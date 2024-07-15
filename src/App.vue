<template>
  <div id="app">
    <div class="section">
      <p>Profiles List</p>
      <div class="flex-row">
        <label class="label" for="filter">Find profile:</label>
        <input class="input">
      </div>
      <div class="buttons">
        <button @click="sortAsc">&#9650; </button>
        <button @click="sortDesc"> &#9660;</button>
      </div>

      <ProfileCard
        v-for="(profile, index) in profiles"
        :key="profile.id"
        :profile="profile"
        class="profile"
      />
    </div>

    <div class="section">
      <p class="header">Add new profile</p>
      <div class="flex-row">
        <label class="label">Name:</label>
        <input class="input">
      </div>
      <div class="flex-row">
        <label class="label" for="filter">Email:</label>
        <input class="input">
      </div>
      <div class="flex-row">
        <label class="label">Specialisation:</label>
        <input class="input">
      </div>
      <button>Add</button>
    </div>
  </div>
</template>

<script>
import ProfileCard from "./components/ProfileCard.vue";

export default {
  name: "App",

  components: {
    ProfileCard
  },

  data() {
    return {
      profiles: [
        {
          id: 1,
          name: "Wojciech",
          email: "wojciech@poz.pl",
          description: "Anaesthesiologist",
          likes: 34
        },
        {
          id: 2,
          name: "Maria",
          email: "maria@poz.pl",
          description: "Radiologist",
          likes: 28
        },
        {
          id: 3,
          name: "Anna",
          email: "anna@poz.pl",
          description: "Surgeon",
          likes: 53
        }
      ]
    };
  },

  methods: {
    sortAsc() {
      this.profiles.sort(function(a, b) {
        return a.likes - b.likes;
      });
    },

    sortDesc() {
      this.profiles.sort(function(a, b) {
        return b.likes - a.likes;
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Roboto", helvetica, arial, sans-serif;
  text-align: center;
  color: white;
  padding: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  position: relative;
  font-size: 1.5em;
}

button {
  display: block;
  padding: 1em;
  width: 100%;
  background-color: rgb(177,215,226);
  border: 1px solid;
  color: #fff;
  cursor: pointer;
  font-size: 0.5em;
  font-weight: 600;
  text-shadow: 0 1px 0 rgba(black, 0.2);
  border-radius: 16px;
}

.content {
  display: flex;
}

.section {
  width: 100%;
  min-width: 300px;
  padding: 2em;
  margin-top: 30px;
  position: relative;
  background: rgba(22,72,99, 0.5);
  border-radius: 16px;
}

.section p {
  margin-bottom: 0.5em;
}

@media screen and (min-width: 600px) {
  .section {
    width: 50vw;
    max-width: 15em;
  }
}

.header {
  color: #fff;
}

.flex-row {
  display: flex;
  margin-bottom: 1em;
}

.label {
  width: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;

  background: rgb(177,215,226);
  border-radius: 16px;
  margin-right: 4px;
}

.input {
  flex: 1;
  padding: 1em;
  border: 0;
  color: #8f8f8f;
  font-size: 1rem;
  border-radius: 16px;
}

.buttons {
  display: flex;
  margin-top: 30px;
}

.buttons button:first-child {
  margin-right: 4px;
}

.buttons button:last-child {
  margin-left: 4px;
}

.profile {
  margin-top: 20px;
}

.icons-note {
  margin-top: 30px;
  font-size: 10px;
}
</style>
