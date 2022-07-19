<template>
  <q-layout view="hHh lpR fFf">

    <q-header 
      elevated 
      class="bg-white" 
      style="height:60px"
    >

      <div class="row flex items-end q-mt-sm">

        <div class="col flex items-center">
          <div class="q-ml-md ">
            <q-avatar size="xl">
              <img src="https://upload.wikimedia.org/wikipedia/en/thumb/0/04/Facebook_f_logo_%282021%29.svg/640px-Facebook_f_logo_%282021%29.svg.png">
            </q-avatar>
          </div>

          <div 
            class="q-ml-sm q-mt-sm"
          >
            <q-input 
              rounded 
              outlined 
              v-model="text" 
              placeholder="Pesquisa no facebook" 
              bg-color="grey-3" 
              dense
            >
               <template v-slot:prepend>
                <q-icon name="search" />
              </template>
            </q-input>
          </div>
        </div>

        <div class="col">
          <div class="q-gutter-y-md" >
            <q-tabs
              v-model="tab"
              indicator-color="secondary"
              class="text-accent"
              size="30px"
            >
              <q-tab name="mails" icon="home" color="grey-4" class="text-secondary my-active-class"/>
              <q-tab name="alarms" icon="video_library" />
              <q-tab name="movies" icon="store" />
              <q-tab name="movies1" icon="account_circle" />

            </q-tabs>
          </div>
        </div>

        <div class="col flex justify-end q-gutter-sm q-mr-md">
          <q-btn 
            round 
            unelevated  
            color="grey-4" 
            text-color="black" 
            icon="apps" 
          />

          <q-btn 
            round 
            unelevated  
            color="grey-4" 
            text-color="black" 
            icon="chat_bubble" 
          >
            <q-badge 
              color="red" 
              floating
            >
              4
            </q-badge>
          </q-btn>

          <q-btn 
            round 
            unelevated 
            color="grey-4" 
            text-color="black" 
            icon="notifications" 
          />
        
          <q-avatar>
            <img src="https://cdn.quasar.dev/img/boy-avatar.png">
          </q-avatar>
          
        </div>
      </div>
  
    </q-header>

    <q-drawer class="bg-grey-3" show-if-above width="250" v-model="leftDrawerOpen" side="left" >
        <q-list class="q-mt-md">
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar>
                <img src="https://cdn.quasar.dev/img/boy-avatar.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>Josué Rufino</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="group" size="md" color="blue"/>
            </q-item-section>

            <q-item-section>Amigos</q-item-section>
          </q-item>

         <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="groups" size="md" color="blue"/>
            </q-item-section>

            <q-item-section>Grupos</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="store" size="md" color="blue"/>
            </q-item-section>

            <q-item-section>Marketplace</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="video_library" size="md" color="blue"/>
            </q-item-section>

            <q-item-section>Watch</q-item-section>
          </q-item>

           <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon name="update" size="md" color="blue"/>
            </q-item-section>

            <q-item-section>Memórias</q-item-section>
          </q-item>

            <q-expansion-item
          switch-toggle-side
          expand-separator
          label="Ver mais"
        >
          <q-card>
            <q-card-section class="bg-grey-3">
              <q-item clickable v-ripple class="q-mr-md">
                  <q-item-section avatar>
                    <q-icon name="video_library" size="md" color="blue"/>
                  </q-item-section>

                  <q-item-section>Watch</q-item-section>
                </q-item>

                <q-item clickable v-ripple>
                  <q-item-section avatar>
                    <q-icon name="update" size="md" color="blue"/>
                  </q-item-section>

                  <q-item-section>Memórias</q-item-section>
                </q-item>
            </q-card-section>
          </q-card>
        </q-expansion-item>

          <q-separator />
        
          <q-toolbar-title class="q-mt-md text-subtitle1" style="color:gray;">Os teus atalhos</q-toolbar-title>
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img src="https://upload.wikimedia.org/wikipedia/pt/9/98/Real_Madrid.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>Real Madrid</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar  size="md" square>
                <img src="https://vuejs.org/images/logo.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>Vue js</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar  size="md">
                <img src="https://img.itdg.com.br/tdg/images/blog/uploads/2017/07/shutterstock_413580649.jpg?w=1200">
              </q-avatar>
            </q-item-section>
            <q-item-section>Comida</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar  size="md">
                <img src="data:image/png;base64,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">
              </q-avatar>
            </q-item-section>
            <q-item-section>Quasar Framework</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar  size="md">
                <img src="https://yt3.ggpht.com/ILlGmw-q2qrWOdcrwkWT90k-pCdj7nAfR9Tts_4eqokXcwMXlWgrsNLCQX6jJlq2iy6nLLWGCQ=s900-c-k-c0x00ffffff-no-rj">
              </q-avatar>
            </q-item-section>
            <q-item-section>NGA</q-item-section>
          </q-item>

          <q-expansion-item
          switch-toggle-side
          expand-separator
          label="Ver mais"
        >
          <q-card>
            <q-card-section class="bg-grey-3">
              <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img src="https://upload.wikimedia.org/wikipedia/pt/9/98/Real_Madrid.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>Real Madrid</q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-avatar  size="md" square>
                <img src="https://vuejs.org/images/logo.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>Vue js</q-item-section>
          </q-item>
            </q-card-section>
          </q-card>
        </q-expansion-item>

      </q-list>
    </q-drawer>

    <q-drawer class="bg-grey-3"  show-if-above width="250" v-model="rightDrawerOpen" side="right">
      <div class="q-mt-md">
        <q-toolbar-title class="text-subtitle1 text-bold text-grey">Patrocinado</q-toolbar-title>
        
        <div class="q-mt-sm flex">
           <img src="https://img.freepik.com/vetores-premium/praca-de-propaganda-de-carros_252779-477.jpg" style="width:100px; border-radius:10px"/> 
           <div class="q-mt-xl q-ml-md" style="line-height:0.5">
            <p>Fale connosco</p>
            <p class="text-grey">grupoautostar.co.ao</p>
           </div>
        </div>

        <div class="q-mt-sm flex">
           <img src="https://santacatarinanews.com/wp-content/uploads/2022/04/mc-picanha-divulgacao-1280x630-1.jpg" style="width:100px;height:90px; border-radius:10px"/> 
           <div class="q-mt-lg q-ml-md" style="line-height:0.5">
            <p>Acpp burger</p>
            <p class="text-grey">burgerangola.co.ao</p>
           </div>
        </div>
      </div>

      <q-separator class="q-mt-md"/>

      <div class="q-mt-md">
        <div class="flex">
           <q-toolbar-title class="text-subtitle1 text-bold text-grey">Pedidos de amizade</q-toolbar-title>
           <p class="q-mr-sm text-blue">Ver tudo</p>
        </div>
        <div class="flex">
           <q-avatar>
              <img src="data:image/jpeg;base64,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">
            </q-avatar>
            <div class="col q-ml-md">
              <q-toolbar-title class="text-bold">Nelma Valdez</q-toolbar-title>
              <p>5 amigos em comum</p>
              <q-btn color="primary" label="Confirmar" style="width:150px;"/>
              <q-btn class="q-mt-sm" color="grey" label="Remover"  text-color="black" style="width:150px;"/>
            </div> 
        </div>
      </div>

      <q-separator class="q-mt-md"/>

      <div>
        <div class="flex">
          <div class="row  q-mt-xs justify-between">
            <q-toolbar-title class="text-subtitle1 text-bold text-grey">Contactos</q-toolbar-title>
            <div class="flex q-ml-xl row q-gutter-sm">
              <q-icon name="video_call" color="grey" size="sm"/>
              <q-icon name="search" color="grey" size="sm"/>
              <q-icon name="more_horiz" color="grey" size="sm"/>
            </div>
          </div>
          <q-list>
              <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Yuri Rego</q-item-section>
              </q-item>

              <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Patricio Wilder</q-item-section>
              </q-item>

              <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Honório Sousa</q-item-section>
              </q-item>

             <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Laurindo Gibui</q-item-section>
              </q-item>

             <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Anilton Fumbwa</q-item-section>
              </q-item>

              <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Júlio Dala</q-item-section>
              </q-item>

              <q-item clickable v-ripple>
                <q-item-section avatar>
                  <q-avatar size="md">
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                  </q-avatar>
                </q-item-section>
                <q-item-section class="text-caption">Geovania Lueji</q-item-section>
              </q-item>
          </q-list>
        </div>
      </div>
    </q-drawer>

    <q-page-container class="bg-grey-3">
      <router-view/>
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      tab: ref('mails')
    }
  }
}
</script>

<style scoped>
  
</style>