<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			this.initLogin();
		},
		onShow: function() {
			console.log('App Show')
		},
		methods:{
			async initLogin(){
				const token = uni.getStorageSync('uniIdToken');
				if(token){
					this.$store.commit('setToken', {
						token
					});
				}
			},
			//打开全局定时器
			openTimer(){
				this.closeTimer();
				__timerId = setInterval(()=>{
					this.$store.commit('setStateAttr', {
						key: 'timerIdent',
						val: !this.$store.state.timerIdent
					})
				}, 1000)
			},
			//关闭定时器
			closeTimer(){
				if(__timerId != 0){
					clearInterval(__timerId);
					__timerId = 0;
				}
			},
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import url("@/common/css/common.css");
</style>
