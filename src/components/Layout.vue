<template>
  <section>
    <nav
      class="navbar is-relative is-transparent py-3"
      aria-label="main navigation"
    >
      <div class="container">
        <div class="navbar-brand">
          <a
            class="navbar-item"
            href="#"
          ><img
            src="metis-assets/logos/metis/metis.svg"
            alt=""
            style="min-height: 40px;"
          ></a>
          <a
            class="navbar-burger"
            role="button"
            type="button"
            data-toggle="side-menu"
            data-target="#sideMenuHeaders07"
            aria-controls="sideMenuHeaders07"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span aria-hidden="true" />
            <span aria-hidden="true" />
            <span aria-hidden="true" />
          </a>
        </div>
        <div class="navbar-menu">
          <div class="navbar-start is-centered-absolute">
            <router-link
              class="navbar-item"
              to="/work-orders"
            >
              Work Order
            </router-link><router-link
              class="navbar-item"
              to="/field-agent"
            >
              Field Agent
            </router-link><router-link
              class="navbar-item"
              to="/report"
            >
              Report
            </router-link><router-link
              class="navbar-item"
              to="/profile"
            >
              Profile
            </router-link>
          </div>
          <div class="navbar-end">
            <div class="navbar-item">
              <div
                v-if="isAuthenticated"
                class="buttons"
              >
                <button
                  class="button is-primary"
                  @click.once="onLogout"
                >
                  Log out
                </button>
              </div>
              <div
                v-else
                class="buttons"
              >
                <router-link
                  class="button is-primary is-outlined"
                  to="/login"
                >
                  Log In
                </router-link><router-link
                  class="button is-primary"
                  to="/register"
                >
                  Sign Up
                </router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
    <div class="section">
      <div class="container">
        <router-view />
      </div>
    </div>
    <div
      id="sideMenuHeaders07"
      class="is-hidden"
    >
      <div
        class="is-fixed is-top is-right is-fullsize has-background-grey"
        style="z-index: 1;"
      />
      <nav
        class="is-fixed is-top is-left is-bottom navbar is-flex is-flex-direction-column pt-4 px-4"
        style="width: 80%; height: 100%; overflow-y: scroll;"
      >
        <div
          class="mb-5 navbar-brand is-flex is-justify-content-space-between"
        >
          <a
            class="navbar-item"
            href="#"
          ><img
            style="min-height: 35px;"
            src="metis-assets/logos/metis/metis.svg"
            alt=""
          ></a>
          <a
            class="navbar-item"
            data-toggle="side-menu"
            data-target="#sideMenuHeaders07"
            aria-controls="sideMenuHeaders07"
            aria-label="Close"
          >
            <svg
              class="image is-24x24"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewbox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </a>
        </div>
        <div>
          <nav class="navbar mb-5">
            <div class="is-fullwidth">
              <router-link
                class="navbar-item"
                to="/work-orders"
              >
                Work Order
              </router-link><router-link
                class="navbar-item"
                to="/field-agent"
              >
                Field Agent
              </router-link><router-link
                class="navbar-item"
                to="/report"
              >
                Report
              </router-link><router-link
                class="navbar-item"
                to="/profile"
              >
                Profile
              </router-link>
            </div>
          </nav>

          <div
            v-if="isAuthenticated"
            class="mb-6 pt-5 has-border-top"
          >
            <button
              class="button is-primary"
              @click.once="onLogout"
            >
              Log out
            </button>
          </div>
          <div
            v-else
            class="mb-6 pt-5 has-border-top"
          >
            <router-link
              class="button is-primary is-outlined"
              to="/login"
            >
              Log In
            </router-link><router-link
              class="button is-primary"
              to="/register"
            >
              Sign Up
            </router-link>
          </div>
        </div>
        <div class="pl-4 pb-4 mt-auto">
          <p class="mb-5 is-size-7">
            <span>Get in Touch</span>
            <a href="#">info@example.com</a>
          </p>
          <a
            href="#"
          ><img
            src="metis-assets/icons/facebook-blue.svg"
            alt=""
          ></a><a
            href="#"
          ><img
            src="metis-assets/icons/twitter-blue.svg"
            alt=""
          ></a><a
            href="#"
          ><img
            src="metis-assets/icons/instagram-blue.svg"
            alt=""
          ></a>
        </div>
      </nav>
    </div>
  </section>
</template>

<script>
import { mapGetters } from "vuex";
export default {
    computed: {
        ...mapGetters("auth", ["isAuthenticated"])
    },
    methods: {
        onLogout() {
            this.$store.dispatch("auth/logout");
        }
    }
};
</script>

<style></style>
