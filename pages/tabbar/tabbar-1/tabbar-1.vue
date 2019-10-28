<template>
	<scroll-view class="content" scroll-y="true" @scrolltoupper="upper" @scrolltolower="lower">
		<view class="scroll-view-item uni-bg-red newsbox">
			<view class=''></view>
		</view>
		
	</scroll-view>
</template>

<script>
export default {
	data() {
		return {
			title: 'Hello'
		};
	},
	onLoad() {
		this.getNews()
	},
	methods: {
		getNews(){
			uni.request({
			    url: 'https://channel.chinanews.com/cns/cjs/cul.shtml',
				method:'GET',
			    data: {
			        pager: 1,
					pagenum:3
			    },
			    success: (res) => {
			        console.log(res.data);
			    }
			});
		},
		upper: function(e) {
			console.log(e,1)
		},
		lower: function(e) {
			console.log(123)
		},
	}
};
</script>

<style>
.content {
	text-align: center;
	height: 100%;
	overflow: hidden;
	/* margin-top: 200upx; */
}
.newsbox{
	display:flex;
	width:100%;
	height:200upx;
	background:#f00;
}
</style>
