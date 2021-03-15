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

<style lang="scss">
	@import "uview-ui/index.scss";
	@import "colorui/main.css";
	@import "colorui/icon.css";d

	/*每个页面公共css */
	.flex {
		display: flex;
	}

	.justify-center {
		justify-content: center;
	}

	.align-center {
		align-items: center;
	}
	page{
		background-color: #FFFFFF;
	}
</style>
