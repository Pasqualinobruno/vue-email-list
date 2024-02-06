<script>
export default {
  name: 'App',
  data() {
    return {
      emails: [],
    }
  },
  mounted() {
    for (let i = 0; i < 10; i++) {
      axios.get('https://flynn.boolean.careers/exercises/api/random/mail')
        .then((response) => {
          //console.log(response);
          this.emails.push(response.data.response)
          //console.log(this.email);
          console.log(this.emails);
        })
    }

  }
}
</script>

<template>
  <div v-for="email in emails">
    <p v-if="emails.length <= 10">{{ email }}</p>
  </div>
</template>

<style scoped></style>
