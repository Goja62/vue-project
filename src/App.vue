<template>
  <section>
    <header><h1>My Friends</h1></header>
    <ul>
      <friend-contact></friend-contact>
      <friend-contact></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 'goja',
          name: 'Zoran Gortnar',
          phone: '2101914',
          email: 'gortnar@beograd.com',
        },
        {
          id: 'jaca',
          name: 'Jasna Knežević',
          phone: '2493112',
          email: 'jasnakn@beograd.com',
        },
      ],
    };
  },
};
</script>
