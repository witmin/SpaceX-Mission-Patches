<template>
    <div>
        <h1>{{ title }}</h1>
        <p class="meta">Through SpaceX data API</p>
        <div>
            <ul class="mission-patches-list">
                <li v-for="mission in missions" :key="mission.flight_number">
                    <img :src="mission.links.mission_patch" :alt="mission.mission_name" class="mission-patch">
                    <p class="launch-year">{{mission.launch_year}}</p>
                  <h2 class="mission-name">{{mission.mission_name}}</h2>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: 'MissionPatches',
        props: {
            msg: String
        },
        data() {
            return {
                title: 'SpaceX Mission Patches',
                info: null,
                missions: null
            }
        },
        mounted() {
            axios
                .get('https://api.spacexdata.com/v2/launches')
                .then(response => (this.info = response, this.missions = response.data))
                .catch(e => {
                    this.errors.push(e)
                })

        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
