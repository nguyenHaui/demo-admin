<template>
  <div>
    <div class="login-box">
      <div class="login-logo">
        <!-- <a href="#">Nam Việt</a> -->
      </div>
      <!-- /.login-logo -->
      <div class="login-box-body">
        <!-- <p class="login-box-msg">Admin</p> -->

        <form v-on:submit.prevent="submitForm">
          <div class="form-group has-feedback">
            <input
              type="text"
              class="form-control"
              placeholder="Tài Khoản"
              v-model="form.name"
            />
            <span
              class="glyphicon glyphicon-envelope form-control-feedback"
            ></span>
          </div>
          <div class="form-group has-feedback">
            <input
              type="password"
              class="form-control"
              placeholder="Mật Khẩu"
              v-model="form.password"
            />
            <span class="glyphicon glyphicon-lock form-control-feedback"></span>
          </div>
          <div class="row">
            <div class="col-xs-8">
              <div class="checkbox icheck">
                <label> <input type="checkbox" /> Remember Me </label>
              </div>
            </div>
            <div class="col-xs-4">
              <button type="submit" class="btn btn-primary btn-block btn-flat">
                Đăng nhập
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "com-login",
  data() {
    return {
      form: {
        name: "",
        password: "",
      },
    };
  },

  methods: {
    submitForm() {
      axios
        .post("http://localhost:8085/api/v1/login", this.form)
        .then((res) => {
          //Perform Success Action
        })
        .catch((error) => {
          // error.response.status Check status code
        })
    },
  },
};
</script>
