<template>
	<div>
		<div class="headerContainer">
			<div class="header">
				<div class="left">
					<img src="../assets/images/logo.png" alt="">
				</div>
				<div class="right">	
					<el-menu
						:default-active="activeIndex"
						mode="horizontal"
						background-color="#23242C"
						text-color="#fff"
						@select="handleSelect"
						>
						<el-menu-item index="1">
							<a href="#homeTop">{{ $t('header.home') }}</a>
						</el-menu-item>
						<el-menu-item index="2">
							<a>{{ $t('header.poc') }}</a>
						</el-menu-item>
						<el-menu-item index="3">
							<a>{{ $t('header.defi') }}</a>
						</el-menu-item>
						<el-menu-item index="4">
							<a>{{ $t('header.Docs') }}</a>
						</el-menu-item>
							<el-menu-item index="5">
							<a>{{ $t('header.News') }}</a>
						</el-menu-item>
							<el-menu-item index="6">
							<a>{{ $t('header.Github') }}</a>
						</el-menu-item>
							<el-menu-item index="7" @click="linkToPDF">
							<a>{{ $t('header.explorer') }}</a>
						</el-menu-item>
						<el-submenu index="8">
							<template slot="title">{{ $t('header.downloads') }}</template>
							<el-menu-item index="8-1">{{ $t('header.downloads') }}</el-menu-item>
							<el-menu-item index="8-2">
								<a @click="linkTogithubLinks('pam')" rel="nofollow" target="_blank" style="font-size:15px;">{{ $t('header.downloads') }}</a>
							</el-menu-item>
						</el-submenu>
						<el-submenu index="9" class="">
							<template slot="title">
								<span class="changeLanguage">
									{{ $t('header.language') }}   
									<span class="arow">></span>
								</span>
							</template>
							<el-menu-item index="zh">简体中文</el-menu-item>
							<el-menu-item index="en">English</el-menu-item>
						</el-submenu>
					</el-menu>
				</div>
			</div>
		</div>
		<div class="empty_Div"></div>
	</div>
</template>
<script>
export default {
	data(){
		return{
			activeIndex: "1"
		}
	},
	methods: {
		 linkToPDF() {
      if (this.$store.state.locale === 'zh') {
        this.$router.push('/zh/test')
      } else {
        this.$router.push('/en/test')
      }
    },
		handleSelect(key) {
		 this.$store.commit('SET_LANG', key)
		 
		 console.log(this.$store.state.locale)
      if (this.$store.state.locale === 'zh') {
        if (this.$route.path.includes('/zh')) {
          return false
        } else {
          this.$router.push(`/zh${this.$route.path}`)
        }
      } else {
				const path = this.$route.path.replace('/zh', '')
        this.$router.push(`${path}`)
      }
		}
	},
	mounted(){
    const self = this
    if (self.$store.state.locale === 'zh') {
    } else if (self.$store.state.locale === 'en') {
      self.$router.push('/en')
    }
	}
	
}
</script>
<style lang="stylus" scoped>
@media screen and (min-width: 420px)
	.headerContainer
		width 100%
		height 60px
		background #23242C
		position fixed
		top 0
		border-bottom 1px solid rgba(151,151,151,1)
		.header
			width 70%
			height 100%
			margin 0 auto
			display flex
			justify-content space-between
			align-items center
			.left
				img 
					height 32px
			.right
				display flex
				justify-content space-between
				align-items center
				.changeLanguage
					border-image linear-gradient(270deg, rgba(255,157,64,1), rgba(255,157,64,1)) 1 1
					border-radius 4px
					border 1px solid #FF9D40
					height 40px
					color #FF7D00
					font-size 14px
					padding  0 13px
					line-height 40px
					display inline-block
					.arow
						margin-left 8px
.empty_Div
	width 100%
	height 60px
</style>