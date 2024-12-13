<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
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
	.page {
	  display: flex;
	  flex-direction: column;
	  justify-content: center;
	  align-items: center;
	  height: 100%;
	}
	.divider-horizon {
	  width: 100%;
	  background-color: #e0e0e0;
	}
	.height-1-px {
	  height: 1px;
	}
</style>
