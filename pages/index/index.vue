<template>
	<view class="container">
		<block v-for="(item, idx) in arrTop3" :key="item">
			<view class="card-empty" v-if="item == null" :data-idx="idx" @click="addTarget">待定目标</view>
			<view class="card-todo" v-else>
				<view class="card-todo-target" :data-idx="idx">{{item.target}}</view>
				<view class="card-todo-description">{{item.description}}</view>
			</view>
		</block>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				title: 'Hello',
				arrTop3: [null, null, null]
			}
		},
		onLoad() {
			console.log("onload")
			console.log(this.arrTop3)
			let arrTop3Stored = uni.getStorageSync('arrTop3')
			if (Array.isArray(arrTop3Stored)) {
				console.log("arrTop3Stored")
				this.arrTop3 = arrTop3Stored;
			}
		},
		methods: {
			addTarget(e) {
				let idx = e.currentTarget.dataset.idx
				console.log("goto newTarget page")
				uni.navigateTo({ url: '/pages/newTarget/newTarget?idx=' + idx })
			}
		}
	}
</script>

<style>
@import '../index/index.css';
</style>
