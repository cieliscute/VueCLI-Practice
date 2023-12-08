<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <CardTest></CardTest>
  <Form v-slot="{ errors, values, validate }" @submit="onSubmit">
    {{ errors }} {{ values }}
    <div class="mb-3">
      <label for="email" class="form-label">Email</label>
      <Field id="email" name="email" type="email" class="form-control" :class="{ 'is-invalid': errors['email'] }"
        placeholder="請輸入 Email" rules="email|required" v-model="user.email"></Field>
      <error-message name="email" class="invalid-feedback"></error-message>
    </div>
    <button class="btn me-2 btn-outline-primary" type="button" @click="validate">驗證</button>
    <button class="btn btn-primary" type="submit">Submit</button>
  </Form>
</template>

<script>
import CardTest from '@/components/CardTest.vue'
export default {
  components: {
    CardTest
  },
  data () {
    return {
      user: {}
    }
  },
  methods: {
    onSubmit () {
      console.log(this.user)
    }
  },
  created () {
    console.log(this.user)
  }
}
</script>
