<template>
	<div class="footer">
		<div class="footer_wrap">
			<div class="footer_wrap_box">
				<div class="footer_wrap_box_flex">
					<p class="footer_wrap_box_flex_title">Developr Resources</p>
					<p class="footer_wrap_box_flex_content">Github</p>
					<p class="footer_wrap_box_flex_content">Developr Doces</p>
					<p class="footer_wrap_box_flex_content">Forum</p>
				</div>
				<div class="footer_wrap_box_flex">
					<p class="footer_wrap_box_flex_title">Coummunity</p>
					<p class="footer_wrap_box_flex_content">Join us</p>
					<p class="footer_wrap_box_flex_content">Meetups</p>
					<p class="footer_wrap_box_flex_content">Request for Comment(RPC)</p>
				</div>
				<div class="footer_wrap_box_flex">
					<p class="footer_wrap_box_flex_title">About</p>
					<p class="footer_wrap_box_flex_content">Dev Business Contace</p>
					<p class="footer_wrap_box_flex_content">Terms Condatinon & Privacy</p>
				</div>
			</div>
		</div>
	</div>
</template>
<style lang="stylus" scoped>
	.footer
		width 100%
		background black 
		height 150px
		padding-top 20px
		padding-bottom 35px
		.footer_wrap
			width 60%
			margin 0 auto
			height 100%
			.footer_wrap_box
				display flex
				justify-content space-between
				height 100%
				.footer_wrap_box_flex
					display flex
					justify-content space-between
					flex-direction column
					.footer_wrap_box_flex_title
						font-weight 500
						color white
						font-size 15px

					.footer_wrap_box_flex_content
						font-size 13px
						color white




</style>