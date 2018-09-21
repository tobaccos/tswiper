<template>
	<div :id="id" class="swiper-container">
		<div class="swiper-wrapper">
			<slot name="swiper-con"></slot>
		</div>
		<!-- Add Pagination -->
		<div :class="pagination"></div>
		<!-- Add Arrows -->
		<div :id="buttonNext" class="swiper-button-next"></div>
		<div :id="buttonPrev" class="swiper-button-prev"></div>
	</div>
</template>

<script>
	import Swiper from "swiper";
	import "swiper/dist/css/swiper.min.css";

	export default {
		name: "tswiper",
		props: {
			id: {
				type: String,
				default: "swiper-container"
			},
			options: {
				type: Object,
				default: () => {}

			},
			pagination: {
				type: String,
				default: "swiper-pagination"
			},
			buttonNext: {
				type: String,
				default: "swiper-button-next"
			},
			buttonPrev: {
				type: String,
				default: "swiper-button-prev"
			},

		},
		data() {
			return {};
		},
		methods: {

		},
		mounted() {
			var _this = this;
			var swiper = new Swiper('#' + _this.id, _this.options);
		}
	};
</script>

<style>
	#swiper-button-next {
		display: none;
	}
	
	#swiper-button-prev {
		display: none;
	}
</style>