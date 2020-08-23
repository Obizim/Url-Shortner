<template>
  <div class="home">
    <div class="landing-page">
      <div class="texts">
        <h1>More than just shorter links</h1>
        <p>
          Build your brand’s recognition and get detailed insights on how your
          links are performing.
        </p>
        <button>Get Started</button>
      </div>
      <img
        src="../assets/images/illustration-working.svg"
        alt="illustration-working"
      />
    </div>

    <section class="shorten-links">
      <form>
        <input
          @keyup="getData"
          type="text"
          placeholder="Shorten a link here .."
          inputmode="url"
        />
        <button @click.prevent="getShortnedUrl">Shorten it</button>
      </form>
    </section>

    <article>
      <div class="heading">
        <h1>Advanced Statistics</h1>
        <p>
          Track how your links are performing across the web with our advanced
          statistics dashboard.
        </p>
      </div>

      <div class="features">
        <div class="feature">
          <img
            src="../assets/images/icon-brand-recognition.svg"
            alt="brand-recognition"
          />
          <div class="texts">
            <h2>Brand Recognition</h2>
            <p>
              Boost your brand recognition with each click. Generic links don’t
              mean a thing. Branded links help instil confidence in your
              content.
            </p>
          </div>
        </div>

        <div class="feature">
          <img
            src="../assets/images/icon-detailed-records.svg"
            alt="detailed records"
          />
          <div class="texts">
            <h2>Detailed Records</h2>
            <p>
              Gain insights into who is clicking your links. Knowing when and
              where people engage with your content helps inform better
              decisions.
            </p>
          </div>
        </div>

        <div class="feature">
          <img
            src="../assets/images/icon-fully-customizable.svg"
            alt="fully-customizable"
          />
          <div class="texts">
            <h2>Fully Customizable</h2>
            <p>
              Improve brand awareness and content discoverability through
              customizable links, supercharging audience engagement.
            </p>
          </div>
        </div>
      </div>
    </article>

    <div class="bookings">
      <h2>Boost your links today</h2>
      <button>Get Started</button>
    </div>

    <footer>
      <div class="footer">
        <div class="footer_list">
          <img id="img" src="../assets/images/logo.svg" alt="logo" />
        </div>

        <ul class="footer_list">
          <p>Features</p>
          <br />

          <li>Link Shortening</li>
          <li>Branded Links</li>
          <li>Analytics</li>
        </ul>

        <ul class="footer_list">
          <p>Resources</p>
          <br />

          <li>Blog</li>
          <li>Developers</li>
          <li>Support</li>
        </ul>

        <ul class="footer_list">
          <p>Company</p>
          <br />

          <li>About</li>
          <li>Our Team</li>
          <li>Careers</li>
          <li>Contact</li>
        </ul>

        <div class="footer_list">
          <div class="footer-img">
            <img src="../assets/images/icon-facebook.svg" alt="facebook" />
            <img src="../assets/images/icon-twitter.svg" alt="twitter" />
            <img src="../assets/images/icon-pinterest.svg" alt="pinterest" />
            <img src="../assets/images/icon-instagram.svg" alt="instagram" />
          </div>
        </div>
      </div>
      <div class="attribution">
        Challenge by
        <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
          >Frontend Mentor</a
        >. Coded with 💖 by <a href="https://github.com/Obizim">Obi Zim</a>.
      </div>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      url: "",
      short: ""
    };
  },
  methods: {
    getData(e) {
      // to get value of input field
      this.url = e.target.value;
    },
    getShortnedUrl() {
      axios
        .post("https://rel.ink/api/links/", {
          url: this.url
        })
        .then(response => {
          this.short = `https://rel.ink/${response.data.hashid}`;
        });
    }
  }
};
</script>
