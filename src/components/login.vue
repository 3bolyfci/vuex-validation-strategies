<template>
    <section class="hero is-primary is-medium">
        <!-- Hero head: will stick at the top -->
        <div class="hero-head">
            <nav class="navbar">
                <div class="container">
                    <div class="navbar-brand">
                        <a class="navbar-item">
                            <img src="https://bulma.io/images/bulma-type-white.png" alt="Logo">
                        </a>
                        <span class="navbar-burger burger" data-target="navbarMenuHeroA">
            <span></span>
            <span></span>
            <span></span>
          </span>
                    </div>
                    <div id="navbarMenuHeroA" class="navbar-menu">
                        <div class="navbar-end">
                            <a class="navbar-item is-active">
                                Home
                            </a>
                            <a class="navbar-item">
                                Examples
                            </a>
                            <a class="navbar-item">
                                Documentation
                            </a>
                            <span class="navbar-item">
              <a class="button is-primary is-inverted">
                <span class="icon">
                  <i class="fab fa-github"></i>
                </span>
                <span>Download</span>
              </a>
            </span>
                        </div>
                    </div>
                </div>
            </nav>
        </div>

        <!-- Hero content: will be in the middle -->
        <div class="hero-body">
            <div class="container has-text-centered">
                <h1 class="title">
                    Login
                </h1>
                <h2 class="subtitle">
                    <div class="field">
                        <label class="label">Name</label>
                        <div class="control has-icons-left has-icons-right">
                            <input class="input" type="email" v-model="firstName" @keyup="submit"
                                   placeholder="Extra small">
                            <span class="icon is-small is-left">
      <i class="fas fa-envelope fa-xs"></i>
    </span>
                            <span class="icon is-small is-right">
      <i class="fas fa-check fa-xs"></i>
    </span>
                        </div>
                    </div>

                </h2>
            </div>
        </div>
    </section>
</template>

<script>
    import {mapActions} from 'vuex'

    export default {
        data() {
            return {
                firstName: undefined
            }
        },
        methods: {
            ...mapActions({
                login :'auth/login'
                }
            ),
            submit() {
                console.log(this.login(this.firstName))
            }
        }
    }
</script>