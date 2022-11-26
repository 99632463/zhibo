<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			// #ifndef MP
			const domModule = weex.requireModule('dom')
			domModule.addRule('fontFace', {
			    'fontFamily': "iconfont",
			    'src': "url('/static/iconfont.ttf')"
			});
			
			// 监听底部导航中间凸起按钮
			uni.onTabBarMidButtonTap(()=>{
				this.authJump({
					url: '/pages/create-live/create-live',
				})
				console.log('点击了中间按钮');
			})
			// #endif
			this.$store.dispatch('initUser')
			
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
	@import url("/common/free.css");
	@import url("/common/common.css");
	/* #ifndef APP-PLUS-NVUE */
	@import url("/common/icon.css");
	/* #endif */
</style>
