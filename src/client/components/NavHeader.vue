<template>
  <div id="navHeader">
    <div class="container">
      <router-link to="/" class="signlink">Just Kanban</router-link>
      <div class="ctrlBtns">
        <BoardsCtrlBtn class="boardCtrlBtn" v-if="isLogin"/>
        <UserCtrlBtn class="userCtrlBtn" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {Component, Vue} from 'vue-property-decorator';;
import { Getter } from 'vuex-class';
import { types as authTypes } from '../store/auth/types';
import BoardsCtrlBtn from './BoardsCtrlBtn.vue';
import UserCtrlBtn from './UserCtrlBtn.vue';

@Component({
  components: {
    BoardsCtrlBtn,
    UserCtrlBtn
  }
})
export default class NavHeader extends Vue {
  @Getter(authTypes.IS_LOGIN) isLogin: boolean
}
</script>

<style lang="scss" scoped>
    #navHeader .container {
        background-color: rgba(0, 0, 0, 0.3);
        padding: 5px 20px;
        height: 45px;
        color: white;
        font-weight: bold;
        display: flex;
        align-items: center;

        .signlink {
            color: white;
            font-family: 'Spicy Rice', cursive;
            font-weight: 100;
            font-size: 32px;
        }

        .ctrlBtns {
            margin-left: auto;
            display: flex;
            align-items: center;

            .userCtrlBtn {
                margin-left: 10px;
            }
        }
    }
</style>

