<template>
	<view class="bg">
		<textarea class="textv" v-model="data.conten" placeholder="倾听你的声音(最长140字)" />
		<view>
			<radio-group name="gender" v-model="data.mood" class="gender">
				<label>
					<radio value="好心情" /><text>好心情</text>
				</label>
				<label style="margin-left: 10%;">
					<radio value="坏心情" /><text>坏心情</text>
				</label>
			</radio-group>
		</view>
		<button type="primary" class="send" @click="get()">发送</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				data:{
					conten:'',
					mood:'',
				}
			}
		},
		onLoad() {
			
		},
		methods: {
			get(){
				uni.request({
					url:"",
					data:this.data,
					success(res) {
						console.log(res);
					}
				})
			}
		}
	}
</script>

<style>

	.textv{
		margin-top: 20%;
		background-color: #F0AD4E;
		margin-left: 10%;
	}
	.gender{
		margin-top: 20%;
		margin-left: 20%;
	}
	.send{
		margin-top: 20%;
	}
</style>
