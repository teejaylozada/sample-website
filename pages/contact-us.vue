<template>
  <div class="master h-screen flex flex-col items-center justify-center text-white text-center px-4 sm:px-10 md:px-12 lg:px-16">
    <!-- ... existing template code ... -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div class="p-6 bg-gray-200 rounded-lg shadow-lg">
        <h2 class="text-3xl font-bold text-blue-900 leading-7">Contact Details</h2>

        <p class="text-gray-700 mt-4">
          HMR Environmental Compound, Silang Industrial Estate Canlubang, Calamba, Laguna, Philippines 4028
        </p>
        <p class="text-blue-900 mt-4">info@fairdinkum.ph</p>
        <p class="text-lg font-semibold text-blue-900 mt-4">+63 2 584 4061 (Local) | +63 2 584 4061 (Manila)</p>
      </div>

      <div class="p-6 bg-gray-200 rounded-lg shadow-lg">
        <h2 class="text-3xl font-bold text-blue-900 font-red-hat-display leading-7">Any Query?</h2>
        <form @submit.prevent="submitForm" class="mt-4">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
            <div>
              <label for="name" class="block text-sm font-medium text-gray-600">Your Name:</label>
              <input type="text" id="name" v-model="form.name" class="mt-1 p-2 w-full border rounded" required>
            </div>
            <div>
              <label for="mobile" class="block text-sm font-medium text-gray-600">Your Mobile:</label>
              <input
                type="text"
                id="mobile"
                v-model="form.mobile_no"
                class="mt-1 p-2 w-full border rounded"
                placeholder="09*********"
                pattern="09\d{9}"
                maxlength="11"
                required
                title="Must be 11 digits (e.g., 09123456789)"
              >
            </div>
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
            <div>
              <label for="email" class="block text-sm font-medium text-gray-600">Your Email Address:</label>
              <input type="email" id="email" v-model="form.email_address" class="mt-1 p-2 w-full border rounded">
            </div>
            <div>
              <label for="subject" class="block text-sm font-medium text-gray-600" required>Subject:</label>
              <input type="text" id="subject" v-model="form.subject" class="mt-1 p-2 w-full border rounded">
            </div>
          </div>
          <div class="mb-4">
            <label for="message" class="block text-sm font-medium text-gray-600">Your Message:</label>
            <textarea id="message" v-model="form.message" class="mt-1 p-2 w-full border rounded"></textarea>
          </div>
          <div class="mb-4 flex justify-center">
            <button class="custom-button text-gray-900 hover:bg-slate-950 hover:text-white py-3 px-6 md:px-8 font-extrabold rounded transition-all transform duration-300 ease-in-out hover:shadow-xl w-full md:w-auto" @click="submitForm">
              Contact Us
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      form: {
        name: "",
        mobile_no: "",
        email_address: "",
        subject: "",
        message: ""
      },
      mobileError: null,
    };
  },

  methods: {
    submitForm() {
      // Check if all required fields are filled
      if (this.form.mobile_no && this.form.name && this.form.email_address && this.form.subject) {
        // All required fields are filled, show success toast
        toast("Form submitted successfully!", {
          autoClose: 2000,
          position: 'top-right',
          type: 'success'
        });
        this.sendEmail(); // Call sendEmail method here
      } else {
        // Not all required fields are filled, show an error toast or handle it as per your requirement
      }
    },

    sendEmail() {
      // Send email if mobile number is valid
      this.$mail.send({
        subject: this.form.subject,
        html: `
          <p>Name: ${this.form.name}</p>
          <p>Mobile No: ${this.form.mobile_no}</p>
          <p>Email Address: ${this.form.email_address}</p>
          <p>Message: ${this.form.message}</p>
        `
      });

      // Clear form fields after sending email
      this.form.name = "";
      this.form.mobile_no = "";
      this.form.email_address = "";
      this.form.subject = "";
      this.form.message = "";

      // Show success notification if needed
    },
  },
};
</script>


<style scoped>

.master {
  background: url('~/assets/sample.jpg');
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
}
</style>
