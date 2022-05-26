<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
        <!-- 網頁標題 -->
      <v-list-item to="/">
        <v-list-item-content>
          <v-list-item-title class="title"> 好友列表(3) </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <!-- 列表 -->
       <v-list two-line>
      <v-list-item-group
        v-model="selected"
        active-class="pink--text"
        multiple
      >
        <template v-for="(item, index) in items">
          <v-list-item :key="item.title">
            <template v-slot:default="{ active }">
              <v-list-item-content>
                <v-container fluid>
                   <v-row
                    align="center"
                    class="spacer"
                    no-gutters
                  >
                    <v-col
                      cols="4"
                      sm="2"
                      md="1"
                    >
                <v-avatar
                  size="30px"
                  
                >
                  <img
                    v-if="item.avatar"
                    alt="Avatar"
                    src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                  >
                  <v-icon
                    v-else
                    :color="item.color"
                    v-text="item.icon"
                  ></v-icon>
                </v-avatar>
              </v-col>
                <v-col 
                class="ml-5">
                  <v-list-item-title v-text="item.title"></v-list-item-title>
                  <v-list-item-subtitle v-text="item.subtitle"></v-list-item-subtitle>
                </v-col>
                </v-row>
                </v-container>

              </v-list-item-content>

              <v-list-item-action>
                <v-list-item-action-text v-text="item.action"></v-list-item-action-text>

              </v-list-item-action>
            </template>
          </v-list-item>

         <!-- 列表底線 -->
          <v-divider
            v-if="index < items.length"
            :key="index"
          ></v-divider>

        </template>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>

<!-- 上框 -->
    <v-card flat>
     <v-container fluid>
      <v-row class="child-flex">
         <div style="flex-basis:80%">
          <v-toolbar color="blue">
            <v-spacer></v-spacer>
             <v-toolbar-title class="white--text">Cherri Chat</v-toolbar-title>
            <v-spacer></v-spacer>

           <div class="text-center">
              <v-btn
                rounded
                color="primary"
                white
              >
                中文
              </v-btn>
            </div>

            <div class="text-center ml-4">
              <v-btn
                rounded
                color="primary"
                dark
              >
               English
              </v-btn>
            </div>
          </v-toolbar>
        </div>
        <div>
          <v-toolbar color="blue">
            <v-avatar
              color="white"
              size="56"
            ></v-avatar>
            <v-toolbar-title class="white--text ml-4">潔西卡</v-toolbar-title>
            <v-spacer></v-spacer>
          </v-toolbar>
        </div>

       
      </v-row>
    </v-container>
  </v-card>
    <v-main class="d-flex justify-center align-center mx-5">
       
          <v-img src="https://i.imgur.com/TQfLgkm.png" width="300px" class="img mb-4"></v-img>
          <span class="text-center cherri-text  blue--text font-weight-medium">開始使用Cherri Chat!</span>
       
         
    </v-main>
  </v-app>
</template>

<style scoped>
  .img {
    margin-left: 35rem;
  }
  .cherri-text{
    margin-left: 36rem;
    margin-top: 20rem;
    font-size: 28px;
  }
@media (max-width: 768px) {
  .img {
    margin-left: 5rem;
  }
   .cherri-text{
    margin-left: 9rem;
    font-size: 20px;
  }
}

</style>

<script>
  export default {
    data: () => ({ 
      drawer: null,
       items: [
        {
          title: '保羅',
          subtitle: `大家好，我是保羅~`,
          avatar: 'https://avatars0.githubusercontent.com/u/9064066?v=4&s=460',
        },
        {
          title: '傑克',
          subtitle: `大家好，我是傑克~`,
          avatar: 'https://avatars0.githubusercontent.com/u/9064066?v=4&s=460',
        },
        {
          title: '傑森',
          subtitle: `大家好，我是傑森~`,
          avatar: 'https://avatars0.githubusercontent.com/u/9064066?v=4&s=460',
        },
      ],
      
      }),
  }
</script>