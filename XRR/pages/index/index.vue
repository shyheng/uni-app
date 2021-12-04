<template>
	<view class="content">
		<view style="float: left;">
			<navigator class="add" url="../add/add">听你说</navigator>
		</view>
		<view>
			<navigator url="../administrator/administrator" class="administrator">删除信息请联系管理员</navigator>
		</view>
		<scroll-view v-for="(item,index) in data" scroll-y="true" class="select">
			<view class="card" style="margin-top: 2%;" @click="details(item)">
				<view class="date" style="float: left;text-align: center;">
					{{item.date}}
				</view>
				<view class="mood" style="color: #85C1E9;text-align: center;">
					{{item.mood}}
				</view>
				<view style="color: #D2B4DE; font-size: 20px; font-family: 宋体;text-align: center;">
					{{item.content}}
				</view>
			</view>
		</scroll-view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				data: []
			}
		},
		onLoad() {
			uni.request({
				url:"",
				success(res) {
					console.log(res);
				}
			})
		},
		methods: {
			details(item){
				console.log(item);
			}
		},
		onPullDownRefresh() {
			uni.request({
				url:"",
				success(res) {
					console.log(res);
				}
			})
		}
	}
</script>

<style>
	.content {
		width: 100%;
		height: auto;
	}

	.add {
		background-color: #007AFF;
		font-size: 30px;
		font-family: "楷体";
	}

	.administrator {
		background-color: #4CD964;
		font-size: 30px;
		font-family: "楷体";
	}

	.select {
		background-color: #EAFAF1;
	}

	.card {
		background-color: #D5F5E3;
	}
</style>
