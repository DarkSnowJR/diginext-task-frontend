<template>
  <div class="profile">
    <div class="card">
      <DoctorIcon class="avatar"/>
      <div class="data">
        <div class="profile-content">
          <div>
            <strong>{{profile.name}}</strong>
            <a :href="profile.email" class="email">{{profile.email}}</a>
          </div>
          <div class="description">{{profile.description}}</div>
        </div>
        <div class="likes">
          <span class="likes-icon">&#10084;</span>
          <span class="likes-value">{{profile.likes}}</span>
        </div>
      </div>
    </div>
    <div class="comment">
      <input class="comment-input" placeholder="Write your comment...">
    </div>
  </div>
</template>

<script>
import DoctorIcon from "./DoctorIcon.vue";

export default {
  name: "ProfileCard",

  components: {
    DoctorIcon
  },

  props: {
    profile: {
      type: Object,
      required: true
    }
  }
};
</script>

<style>
.card {
  display: flex;
  align-items: center;
  border: solid 1px rgb(172, 172, 172);
  border-radius: 3px;
  padding: 10px;
  font-size: 14px;
  color: rgb(82, 82, 82);
  background-color: #fff;
  border-radius: 16px 16px 0 0;
}

.avatar {
  width: 64px;
  min-width: 64px;
  height: 64px;
  border: 1px solid rgb(172, 172, 172);
  border-radius: 100%;
}

.data {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.profile-content {
  display: flex;
  flex-direction: column;
  text-align: left;
  margin-left: 15px;
}

.email {
  margin-left: 15px;
  color: rgb(66,125,157);
  font-weight: bold;
}

.description {
  margin-top: 5px;
}

.likes {
  color: rgb(66,125,157);
  margin-top: 10px;
  margin-left: 15px;
}

.likes-value {
  margin-left: 5px;
}

.comment {
  display: flex;
  width: 100%;
}

.comment-input {
  width: 100%;
  border-radius: 0 0 16px 16px;
  padding: 8px;
  border: 0;
}
</style>
