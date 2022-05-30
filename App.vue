<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			if (!wx.cloud) {
				console.error('请使用 2.2.3 或以上的基础库以使用云能力');
			} else {
				wx.cloud.init({
					env: 'lh-xcxkfds-3g3e3agda56584c9',
					traceUser: true,
				});
			}
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
