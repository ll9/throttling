<template>
  <Page>
    <ActionBar title="Welcome to NativeScript-Vue!"/>
    <StackLayout>
      <Button ref="test" text="throttle" @tap="throttle"/>
    </StackLayout>
  </Page>
</template>

<script>
var _ = require("lodash");

export default {
  data() {
    return {
      msg: "Hello World!"
    };
  },
  methods: {
    throttle: _.debounce(() => {
      console.log('I get fired every two seconds!')
    }, 2000, {leading: true}, {trailing: false}),
    //   console.log("Throttle should be called");
    //   console.log(JSON.stringify(_.partition([1, 2, 3, 4], n => n % 2)));
    //   console.log(this.$refs.test.nativeView.text);
    // //   this.$refs.test.nativeView.text = "throttle234";
    //   _.throttle(() => {
    //     this.$refs.test.nativeView.text = "throttle24";
    //     console.log("Throtted");
    //   }, 150);
    // }
  }
};
</script>

<style scoped>
ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}
</style>
