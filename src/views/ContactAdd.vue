<template>
	<div class="page">
		<div>
			<h3 class="p-10">Thông tin người nhận</h3>
			<ContactForm
				:contact="{}"
				:resetAfterSubmit="false"
				@submit:contact="saveContact"
			/>
		</div>
	</div>
</template>

<script>
import { swtoast } from "@/mixins/swal.mixin";
import ContactForm from "@/components/ContactForm.vue";
import ContactService from "@/services/contact.service";

export default {
	components: {
		ContactForm,
	},
	methods: {
		async saveContact(data) {
			try {
				await ContactService.create(data);
				swtoast.success({
					text: "Thông tin được thêm thành công.",
				});
			} catch (error) {
				console.log(error);
				swtoast.error({
				text: "Bị lỗi, vui lòng kiểm tra lại.",
				});
			}
		},
	},
};
</script>
<style scoped>
h3{
	color:#849530;
	font-family: Arial, Helvetica, sans-serif;
	margin-left:110px;
	margin-top:50px;
}
</style>>