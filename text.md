VUEX

    const store = new Vuex.Store({
      state: {
        count: 0
      },
      mutations: {
        increment (state) {
          state.count++
        }
      }
    })

    store.commit('increment')
    console.log(store.state.count) // -> 1


一、VUEX的简单入门

     computed: {
        count () {
          return this.$store.state.count
        }
      }



二、状态与data的组合  

     computed: mapState({
        // 箭头函数可使代码更简练
        count: state => state.count,
    
        // 传字符串参数 'count' 等同于 `state => state.count`
        countAlias: 'count',
    
        // 为了能够使用 `this` 获取局部状态，必须使用常规函数
        countPlusLocalState (state) {
          return state.count + this.localCount
        }
      })

三、mapState的引用

    computed: mapState([
      // 映射 this.count 为 store.state.count
      'count'
    ])

四、…mapState的引用

    computed: {
      localComputed () { /* ... */ },
      // 使用对象展开运算符将此对象混入到外部对象中
      ...mapState({
        // ...
      })
    }


五、Getter

六、mapGetters 辅助函数

七、Mutation

八、Action

九、Module



