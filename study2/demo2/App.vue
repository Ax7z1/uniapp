<script>
	export default {
		onLaunch: function() {
			uni.setTabBarStyle({
				// color:"#c00",
				// backgroundColor:"#0c0"
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
