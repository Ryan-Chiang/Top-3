<template>
	<view class="page">
		<!-- 表单，包括单行的目标、 多行的描述-->
		<form @submit="addTarget">
			<input type="text" name="target" placeholder="目标" />
			<view class="divider-horizon height-1-px"></view>
			<textarea name="description" placeholder="描述"></textarea>
			<button form-type="submit" type ="button" >提交</button>
		</form>
	</view>
</template>

<script>
export default {
	data() {
		return {
			idxTarget: null
		}
	},
	onLoad(e) {
		this.idxTarget = e.idx
	},
	methods: {
		addTarget(e) {
			// 获取表单数据
			let formData = e.detail.value
			// 获取目标的索引
			let idx = this.$route.query.idx
			// 获取目标列表
			let arrTop3 = uni.getStorageSync('arrTop3')
			// 如果目标列表不存在，创建一个空列表
			if (!arrTop3) {
				arrTop3 = [null, null, null]
			}
			// 更新目标列表
			arrTop3[idx] = formData
			uni.setStorageSync('arrTop3', arrTop3)
			// 返回上一页
			uni.navigateBack()
		}
	}
}
</script>

<style>

</style>
