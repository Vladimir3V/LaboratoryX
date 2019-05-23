<template>
    <div class="home">

      <div class="container">

        <h1 class="title"></h1>
 


        <div class="subtitle box is-6">
          <ul>
            <li>Click on the order to get a detailed description.</li>
            <li>Contact with the order owner to ask him to add you as a freelancer for his order (contact information you will find in the detailed description).</li>
            <li>You can check orders assigned to you on "Assigned Order" page.</li>
          </ul>
        </div>

        <div class="subtitle box is-6">

        <div class="subtitle box is-6">
          <iframe width="480" height="360" src="https://www.youtube.com/embed/xFa2_PVMeDQ" frameborder="0" allowfullscreen></iframe>
        </div>

            <nav class="level subtitle">

                <div class="level-item has-text-centered">
                    <div>
                        <p class="heading">By ID</p>
                        <input class="input is-small" type="text" v-model="idFilter">
                    </div>
                </div>

                <div class="level-item has-text-centered">
                    <div>
                        <p class="heading">By Title</p>
                        <input class="input is-small" type="text" v-model="titleFilter">
                    </div>
                </div>
            
                <div class="level-item has-text-centered">
                    <div>
                        <p class="heading">By Email</p>
                        <input class="input is-small" type="email" v-model="emailFilter">
                    </div>
                </div>

                <div class="level-item has-text-centered">
                    <div>
                        <p class="heading">By Address</p>
                        <input class="input is-small" type="text" v-model="addressFilter">
                    </div>
                </div>
                
            </nav>

        </div>
      
      </div>

      <div class="container">
        <div class="columns" v-if="orders">
            <home-order-card v-for="order in orderedOrders"
                v-bind:key="order.id"
                v-if="!order.owner_lock && !order.freelancer_lock"
                v-bind:orderData="order"></home-order-card>
        </div>
      </div>

    </div>
</template>



<style lang="sass" scoped>
@import "../mq"

.container
  margin-top: 1.1em

.title
  margin-bottom: 1.1em

.box
  margin-bottom: 1.1em

ul
  list-style: circle
  margin-left: 1.1em  

.table
  flex-wrap: wrap

.column
  overflow: auto

.columns
  flex-wrap: wrap
</style>