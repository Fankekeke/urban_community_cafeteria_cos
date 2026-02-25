<template>
  <a-row :gutter="16" style="width: 100%">
    <a-col :span="6">
      <!-- 美化后的订单列表 -->
      <a-list
        item-layout="vertical"
        :data-source="orders"
        bordered
        class="order-list"
      >
        <a-list-item slot="renderItem" slot-scope="item, index" class="order-item">
          <a-card hoverable class="order-card">
            <a-card-meta>
              <template #title>
                <span class="order-code">订单 {{ index + 1 }}: {{ item.code }}</span>
              </template>
              <template #description>
                <div class="order-details">
                  <p><a-icon type="environment" /> 地址: {{ item.address }}</p>
                  <p><a-icon type="car" /> 距离: {{ item.kilometre }} km</p>
                  <p><a-icon type="dollar" /> 配送费: ¥{{ item.distributionPrice }}</p>
                </div>
              </template>
            </a-card-meta>
          </a-card>
        </a-list-item>
      </a-list>
    </a-col>
    <a-col :span="18">
      <div id="route-map" style="height: 400px; width: 100%;"></div>
    </a-col>
  </a-row>
</template>

<script>import { mapState } from 'vuex'

export default {
  name: 'Delivery',
  data () {
    return {
      map: null,
      orders: [], // 存储订单数据
      distances: {} // 存储距离信息
    }
  },
  computed: {
    ...mapState({
      currentUser: state => state.account.user
    })
  },
  mounted () {
    this.queryDeliveryOrder()
    this.initRouteMap()
  },
  methods: {
    queryDeliveryOrder () {
      this.$get('/cos/order-info/queryDeliveryOrder', { userId: this.currentUser.userId }).then(res => {
        this.orders = res.data.orders || []
        this.distances = res.data.distances || {}
        this.planRoute() // 查询成功后规划路线
      })
    },
    initRouteMap () {
      this.map = new BMapGL.Map('route-map')
      this.map.centerAndZoom(new BMapGL.Point(116.404, 39.915), 12)
      this.map.enableScrollWheelZoom(true)
    },

    planRoute () {
      if (!this.orders.length) return

      const driving = new BMapGL.DrivingRoute(this.map, {
        renderOptions: {
          map: this.map,
          autoViewport: true
        }
      })

      // 构造路线点数组
      const waypoints = this.orders.map((order, index) => {
        const startPoint = new BMapGL.Point(order.startLongitude, order.startLatitude)
        const endPoint = new BMapGL.Point(order.endLongitude, order.endLatitude)

        // 在地图上标记起点和终点
        this.addMarker(startPoint, `订单 ${index + 1} 起点`)
        this.addMarker(endPoint, `订单 ${index + 1} 终点`)

        return startPoint
      })

      // 添加终点
      const finalEndPoint = new BMapGL.Point(
        this.orders[this.orders.length - 1].endLongitude,
        this.orders[this.orders.length - 1].endLatitude
      )

      // 规划路线
      driving.search(waypoints[0], finalEndPoint, { waypoints: waypoints.slice(1) })
    },

    addMarker (point, label) {
      const marker = new BMapGL.Marker(point)
      const labelObj = new BMapGL.Label(label, {
        position: point,
        offset: new BMapGL.Size(20, -10)
      })
      labelObj.setStyle({
        color: '#fff',
        backgroundColor: '#1890ff',
        border: 'none',
        borderRadius: '4px',
        padding: '4px 8px'
      })
      this.map.addOverlay(marker)
      this.map.addOverlay(labelObj)
    }
  }
}
</script>

<style scoped>.order-list {
  background-color: #f9f9f9;
  border-radius: 8px;
  overflow: hidden;
}

.order-item {
  margin-bottom: 16px;
}

.order-card {
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.order-card:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transform: translateY(-2px);
}

.order-code {
  font-size: 16px;
  font-weight: bold;
  color: #1890ff;
}

.order-details p {
  margin: 4px 0;
  font-size: 14px;
  color: #555;
}

.order-details .anticon {
  margin-right: 6px;
  color: #1890ff;
}

.order-code {
  font-size: 16px;
  font-weight: bold;
  color: #1890ff;
}

.order-details p {
  margin: 4px 0;
  font-size: 14px;
  color: #555;
}

.order-details .anticon {
  margin-right: 6px;
  color: #1890ff;
}
</style>
