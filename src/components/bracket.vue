<template>
    <div class="component">
        <div id="bracket" class="container-fluid">
            <div class="row justify-content-start">
                <div class="round-1-left mycol-1">
                    <div v-for="(match, index) in 8" v-bind:key="index" class="match round1 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[matches[index][0][2]>0 ? 'win' : 'lose',{played:played1},matches[index][0][0],{teamhover:matches[index][0][4]}]" @mouseover="hovteam(matches[index][0][4])">
                            <span class="seed">{{matches[index][0][3]}}</span> <span>{{matches[index][0][0]}}</span> <em class="score">{{matches[index][0][1]}}</em>
                        </p>
                        <div class="spacer-1"></div>
                        <p class="slot slot2" :class="[matches[index][1][2]>0 ? 'win' : 'lose',{played:played1},matches[index][1][0]]">
                            <span class="seed">{{matches[index][1][3]}} </span> <span>{{matches[index][1][0]}}</span> <em class="score">{{matches[index][1][1]}}</em>
                        </p>
                    </div>
                </div> 
                <div class="round-2-left mycol-1">
                    <div class="round-2-offset"></div>
                    <div v-for="(match, index) in 4" v-bind:key="index" class="match round2 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round2[index][0][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index][0][0]]">
                            <span class="seed">{{round2[index][0][3]}}</span> <span>{{round2[index][0][0]}}</span> <em class="score">{{round2[index][0][1]}}</em>
                        </p>
                        <div class="spacer-2"></div>
                        <p class="slot slot2" :class="[round2[index][1][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index][1][0]]">
                            <span class="seed">{{round2[index][1][3]}} </span> <span>{{round2[index][1][0]}}</span> <em class="score">{{round2[index][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-3-left mycol-1">
                    <div class="round-3-offset"></div>
                    <div v-for="(match, index) in 2" v-bind:key="index" class="match round3 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round3[index][0][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index][0][0]]">
                            <span class="seed">{{round3[index][0][3]}}</span> <span>{{round3[index][0][0]}}</span> <em class="score">{{round3[index][0][1]}}</em>
                        </p>
                        <div class="spacer-3"></div>
                        <p class="slot slot2" :class="[round3[index][1][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index][1][0]]">
                            <span class="seed">{{round3[index][1][3]}} </span> <span>{{round3[index][1][0]}}</span> <em class="score">{{round3[index][1][1]}}</em>
                        </p>
                    </div>
                </div>   
                <div class="round-4-left mycol-1">
                    <div class="round-4-offset"></div>
                    <div v-for="(match, index) in 1" v-bind:key="index" class="match round4 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round4[index][0][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index][0][0]]">
                            <span class="seed">{{round4[index][0][3]}}</span> <span>{{round4[index][0][0]}}</span> <em class="score">{{round4[index][0][1]}}</em>
                        </p>
                        <div class="spacer-4"></div>
                        <p class="slot slot2" :class="[round4[index][1][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index][1][0]]">
                            <span class="seed">{{round4[index][1][3]}} </span> <span>{{round4[index][1][0]}}</span> <em class="score">{{round4[index][1][1]}}</em>
                        </p>
                    </div>
                </div>
                <div class="center-seperator"></div>
                <div class="round-4-right right mycol-1">
                    <div class="round-4-offset"></div>
                    <div v-for="(match, index) in 1" v-bind:key="index" class="match round4 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round4[index+1][0][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+1][0][0]]">
                            <span class="seed">{{round4[index+1][0][3]}}</span> <span>{{round4[index+1][0][0]}}</span> <em class="score">{{round4[index+1][0][1]}}</em>
                        </p>
                        <div class="spacer-4"></div>
                        <p class="slot slot2" :class="[round4[index+1][1][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+1][1][0]]">
                            <span class="seed">{{round4[index+1][1][3]}} </span> <span>{{round4[index+1][1][0]}}</span> <em class="score">{{round4[index+1][1][1]}}</em>
                        </p>
                    </div>
                </div>
                <div class="round-3-right right mycol-1">
                    <div class="round-3-offset"></div>
                    <div v-for="(match, index) in 2" v-bind:key="index" class="match round3 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round3[index+2][0][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+2][0][0]]">
                            <span class="seed">{{round3[index+2][0][3]}}</span> <span>{{round3[index+2][0][0]}}</span> <em class="score">{{round3[index+2][0][1]}}</em>
                        </p>
                        <div class="spacer-3"></div>
                        <p class="slot slot2" :class="[round3[index+2][1][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+2][1][0]]">
                            <span class="seed">{{round3[index+2][1][3]}} </span> <span>{{round3[index+2][1][0]}}</span> <em class="score">{{round3[index+2][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-2-right right mycol-1">
                    <div class="round-2-offset"></div>
                    <div v-for="(match, index) in 4" v-bind:key="index" class="match round2 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round2[index+4][0][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+4][0][0]]">
                            <span class="seed">{{round2[index+4][0][3]}}</span> <span>{{round2[index+4][0][0]}}</span> <em class="score">{{round2[index+4][0][1]}}</em>
                        </p>
                        <div class="spacer-2"></div>
                        <p class="slot slot2" :class="[round2[index+4][1][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+4][1][0]]">
                            <span class="seed">{{round2[index+4][1][3]}} </span> <span>{{round2[index+4][1][0]}}</span> <em class="score">{{round2[index+4][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-1-right right mycol-1">
                    <div v-for="(match, index) in 8" v-bind:key="index" class="match round1 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[matches[index+8][0][2]>0 ? 'win' : 'lose',{played:played1},matches[index+8][0][0]]">
                            <span class="seed">{{matches[index+8][0][3]}}</span> <span>{{matches[index+8][0][0]}}</span> <em class="score">{{matches[index+8][0][1]}}</em>
                        </p>
                        <div class="spacer-1"></div>
                        <p class="slot slot2" :class="[matches[index+8][1][2]>0 ? 'win' : 'lose',{played:played1},matches[index+8][1][0]]">
                            <span class="seed">{{matches[index+8][1][3]}} </span> <span>{{matches[index+8][1][0]}}</span> <em class="score">{{matches[index+8][1][1]}}</em>
                        </p>
                    </div>
                </div> 
            </div>
            <div class="row justify-content-center final-four">
                <div class="round-3-left col-2 match round3 final-four-match">
                    <p class="slot slot1" :class="[round5[0][0][2]>4 ? 'win' : 'lose',{played:played5},{hideslot:!show5},round5[0][0][0]]">
                        <span class="seed">{{round5[0][0][3]}}</span> <span>{{round5[0][0][0]}}</span> <em class="score">{{round5[0][0][1]}}</em>
                    </p>
                    <div class="spacer-3"></div>
                    <p class="slot slot2" :class="[round5[0][1][2]>4 ? 'win' : 'lose',{played:played5},{hideslot:!show5},round5[0][1][0]]">
                        <span class="seed">{{round5[0][1][3]}}</span> <span>{{round5[0][1][0]}}</span> <em class="score">{{round5[0][1][1]}}</em>
                    </p>
                </div>  
                <div class="col-2 center px-0">
                    <div class="champ-top px-2">
                        <p style="padding-top:38px" :class="[round6[0][0][2]>5 ? 'win' : 'lose',{played:played6},{hideslot:!show6},round6[0][0][3]]">
                            <span class="float-left"><span class="seed">{{round6[0][0][3]}}</span> <span>{{round6[0][0][0]}}</span> </span><em class="score">{{round6[0][0][1]}}</em>
                        </p>
                    </div>
                    <div class="championship ">
                        <div></div>
                    </div>
                    <div class="champ-bottom px-2">
                        <p style="padding-top:1px" :class="[round6[0][1][2]>5 ? 'win' : 'lose',{played:played6},{hideslot:!show6},round6[0][1][3]]">
                            <span class="float-left"><span class="seed">{{round6[0][1][3]}}</span> <span>{{round6[0][1][0]}}</span> </span><em class="score">{{round6[0][1][1]}}</em>
                        </p>
                    </div>
                </div>
                <div class="right col-2">
                    <div class="round-3-right  match round3 final-four-match">
                        <p class="slot slot1" :class="[round5[1][0][2]>4 ? 'win' : 'lose',{played:played5},{hideslot:!show5},round5[1][0][0]]">
                            <span class="seed">{{round5[1][0][3]}}</span> <span>{{round5[1][0][0]}}</span> <em class="score">{{round5[1][0][1]}}</em>
                        </p>
                        <div class="spacer-3"></div>
                        <p class="slot slot2" :class="[round5[1][1][2]>4 ? 'win' : 'lose',{played:played5},{hideslot:!show5},round5[1][1][0]]">
                            <span class="seed">{{round5[1][1][3]}} </span> <span>{{round5[1][1][0]}}</span> <em class="score">{{round5[1][1][1]}}</em>
                        </p>
                    </div>
                </div> 
            </div>
            <div class="row justify-content-start">
                <div class="round-1-left mycol-1">
                    <div v-for="(match, index) in 8" v-bind:key="index" class="match round1 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[matches[index+16][0][2]>0 ? 'win' : 'lose',{played:played1},matches[index+16][0][0]]">
                            <span class="seed">{{matches[index+16][0][3]}}</span> <span>{{matches[index+16][0][0]}}</span> <em class="score">{{matches[index+16][0][1]}}</em>
                        </p>
                        <div class="spacer-1"></div>
                        <p class="slot slot2" :class="[matches[index+16][1][2]>0 ? 'win' : 'lose',{played:played1},matches[index+16][1][0]]">
                            <span class="seed">{{matches[index+16][1][3]}} </span> <span>{{matches[index+16][1][0]}}</span> <em class="score">{{matches[index+16][1][1]}}</em>
                        </p>
                    </div>
                </div> 
                <div class="round-2-left mycol-1">
                    <div class="round-2-offset"></div>
                    <div v-for="(match, index) in 4" v-bind:key="index" class="match round2 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round2[index+8][0][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+8][0][0]]">
                            <span class="seed">{{round2[index+8][0][3]}}</span> <span>{{round2[index+8][0][0]}}</span> <em class="score">{{round2[index+8][0][1]}}</em>
                        </p>
                        <div class="spacer-2"></div>
                        <p class="slot slot2" :class="[round2[index+8][1][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+8][1][0]]">
                            <span class="seed">{{round2[index+8][1][3]}} </span> <span>{{round2[index+8][1][0]}}</span> <em class="score">{{round2[index+8][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-3-left mycol-1">
                    <div class="round-3-offset"></div>
                    <div v-for="(match, index) in 2" v-bind:key="index" class="match round3 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round3[index+4][0][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+4][0][0]]">
                            <span class="seed">{{round3[index+4][0][3]}}</span> <span>{{round3[index+4][0][0]}}</span> <em class="score">{{round3[index+4][0][1]}}</em>
                        </p>
                        <div class="spacer-3"></div>
                        <p class="slot slot2" :class="[round3[index+4][1][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+4][1][0]]">
                            <span class="seed">{{round3[index+4][1][3]}} </span> <span>{{round3[index+4][1][0]}}</span> <em class="score">{{round3[index+4][1][1]}}</em>
                        </p>
                    </div>
                </div>   
                <div class="round-4-left mycol-1">
                    <div class="round-4-offset"></div>
                    <div v-for="(match, index) in 1" v-bind:key="index" class="match round4 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round4[index+2][0][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+2][0][0]]">
                            <span class="seed">{{round4[index+2][0][3]}}</span> <span>{{round4[index+2][0][0]}}</span> <em class="score">{{round4[index+2][0][1]}}</em>
                        </p>
                        <div class="spacer-4"></div>
                        <p class="slot slot2" :class="[round4[index+2][1][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+2][1][0]]">
                            <span class="seed">{{round4[index+2][1][3]}} </span> <span>{{round4[index+2][1][0]}}</span> <em class="score">{{round4[index+2][1][1]}}</em>
                        </p>
                    </div>
                </div>
                <div class="center-seperator"></div>
                <div class="round-4-right right mycol-1">
                    <div class="round-4-offset"></div>
                    <div v-for="(match, index) in 1" v-bind:key="index" class="match round4 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round4[index+3][0][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+3][0][0]]">
                            <span class="seed">{{round4[index+3][0][3]}}</span> <span>{{round4[index+3][0][0]}}</span> <em class="score">{{round4[index+3][0][1]}}</em>
                        </p>
                        <div class="spacer-4"></div>
                        <p class="slot slot2" :class="[round4[index+3][1][2]>3 ? 'win' : 'lose',{played:played4},{hideslot:!show4},round4[index+3][1][0]]">
                            <span class="seed">{{round4[index+3][1][3]}} </span> <span>{{round4[index+3][1][0]}}</span> <em class="score">{{round4[index+3][1][1]}}</em>
                        </p>
                    </div>
                </div>
                <div class="round-3-right right mycol-1">
                    <div class="round-3-offset"></div>
                    <div v-for="(match, index) in 2" v-bind:key="index" class="match round3 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round3[index+6][0][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+6][0][0]]">
                            <span class="seed">{{round3[index+6][0][3]}}</span> <span>{{round3[index+6][0][0]}}</span> <em class="score">{{round3[index+6][0][1]}}</em>
                        </p>
                        <div class="spacer-3"></div>
                        <p class="slot slot2" :class="[round3[index+6][1][2]>2 ? 'win' : 'lose',{played:played3},{hideslot:!show3},round3[index+6][1][0]]">
                            <span class="seed">{{round3[index+6][1][3]}} </span> <span>{{round3[index+6][1][0]}}</span> <em class="score">{{round3[index+6][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-2-right right mycol-1">
                    <div class="round-2-offset"></div>
                    <div v-for="(match, index) in 4" v-bind:key="index" class="match round2 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[round2[index+12][0][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+12][0][0]]">
                            <span class="seed">{{round2[index+12][0][3]}}</span> <span>{{round2[index+12][0][0]}}</span> <em class="score">{{round2[index+12][0][1]}}</em>
                        </p>
                        <div class="spacer-2"></div>
                        <p class="slot slot2" :class="[round2[index+12][1][2]>1 ? 'win' : 'lose',{played:played2},{hideslot:!show2},round2[index+12][1][0]]">
                            <span class="seed">{{round2[index+12][1][3]}} </span> <span>{{round2[index+12][1][0]}}</span> <em class="score">{{round2[index+12][1][1]}}</em>
                        </p>
                    </div>
                </div>  
                <div class="round-1-right right mycol-1">
                    <div v-for="(match, index) in 8" v-bind:key="index" class="match round1 row">
                        <!--<div :class="'m'+index" class="match"> -->
                        <p class="slot slot1" :class="[matches[index+24][0][2]>0 ? 'win' : 'lose',{played:played1},matches[index+24][0][0]]">
                            <span class="seed">{{matches[index+24][0][3]}}</span> <span>{{matches[index+24][0][0]}}</span> <em class="score">{{matches[index+24][0][1]}}</em>
                        </p>
                        <div class="spacer-1"></div>
                        <p class="slot slot2" :class="[matches[index+24][1][2]>0 ? 'win' : 'lose',{played:played1},matches[index+24][1][0]]">
                            <span class="seed">{{matches[index+24][1][3]}} </span> <span>{{matches[index+24][1][0]}}</span> <em class="score">{{matches[index+24][1][1]}}</em>
                        </p>
                    </div>
                </div> 
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data:function(){
            return{
                teams:[
                    ["Duke",96.3,0,1,false],
                    ["North Dakota State",70.35,0,16,false],
                    ["Virginia Commonwealth",82.23,0,8,false],
                    ["Central Florida",81.72,0,9,false],
                    ["Mississippi State",86.44,0,5,false],
                    ["Liberty",78.01,0,12,false],
                    ["Virginia Tech",88.74,0,4,false],
                    ["Saint Louis",77.35,0,13,false],
                    ["Maryland",84.84,0,6,false],
                    ["Belmont",81.06,0,11,false],
                    ["Louisiana State",86.41,0,3,false],
                    ["Yale",76.89,0,14,false],
                    ["Louisville",85.9,0,7,false],
                    ["Minnesota",81.19,0,10,false],
                    ["Michigan State",92.19,0,2,false],
                    ["Bradley",72.91,0,15,false],
                    ["Gonzaga",95,0,1,false],
                    ["Fairleigh Dickinson",70.04,0,16,false],
                    ["Syracuse",83.92,0,8,false],
                    ["Baylor",82.71,0,9,false],
                    ["Marquette",85.31,0,5,false],
                    ["Murray State",81.29,0,12,false],
                    ["Florida State",88.39,0,4,false],
                    ["Vermont",79.29,0,13,false],
                    ["Buffalo",85.75,0,6,false],
                    ["Arizona State",80.87,0,11,false],
                    ["Texas Tech",89.65,0,3,false],
                    ["Northern Kentucky",77.25,0,14,false],
                    ["Nevada",86.12,0,7,false],
                    ["Florida",83.95,0,10,false],
                    ["Michigan",91.13,0,2,false],
                    ["Montana",76.19,0,15,false],
                    ["Virginia",95.2,0,1,false],
                    ["Gardner-Webb",71.75,0,16,false],
                    ["Mississippi",81.64,0,8,false],
                    ["Oklahoma",83.01,0,9,false],
                    ["Wisconsin",86.7,0,5,false],
                    ["Oregon",84.02,0,12,false],
                    ["Kansas State",86.66,0,4,false],
                    ["UC-Irvine",78.35,0,13,false],
                    ["Villanova",86.95,0,6,false],
                    ["Saint Mary's (CA)",83.58,0,11,false],
                    ["Purdue",89.09,0,3,false],
                    ["Old Dominion",77.07,0,14,false],
                    ["Cincinnati",85.12,0,7,false],
                    ["Iowa",82.4,0,10,false],
                    ["Tennessee",91.65,0,2,false],
                    ["Colgate",74.95,0,15,false],
                    ["North Carolina",93.25,0,1,false],
                    ["Iona",71.86,0,16,false],
                    ["Utah State",82.28,0,8,false],
                    ["Washington",82.55,0,9,false],
                    ["Auburn",88.65,0,5,false],
                    ["New Mexico State",80.91,0,12,false],
                    ["Kansas",86.3,0,4,false],
                    ["Northeastern",78.58,0,13,false],
                    ["Iowa State",86.16,0,6,false],
                    ["Ohio State",82.59,0,11,false],
                    ["Houston",88.13,0,3,false],
                    ["Georgia State",76.13,0,14,false],
                    ["Wofford",84.38,0,7,false],
                    ["Seton Hall",82.18,0,10,false],
                    ["Kentucky",91.24,0,2,false],
                    ["Abilene Christian",72.33,0,15,false]
                ],
                matches:[],
                round2:[],
                round3:[],
                round4:[],
                round5:[],
                round6:[],
                played1:false,
                played2:false,
                played3:false,
                played4:false,
                played5:false,
                played6:false,
                show2:false,
                show3:false,
                show4:false,
                show5:false,
                show6:false,
                roundCount:0,
            }
        },
        props: {
            
        },
        methods:{
            hovteam(team){
                team = true;
                console.log(team)
            },
            test(){
                for(var i =0; i < 64; i=i+2){
                    var hold = [];
                    hold.push(this.teams[i],this.teams[i+1]);
                    this.matches.push(hold);
                }
            console.log(this.matches);
            },
            simFirstRound(){
                console.log("first")
                for(var i =0; i < 32; i=i+2){
                    var hold = [];
                    var odds = 1/(1+10**((-(this.matches[i][0][1]-this.matches[i][1][1]))*30.464/400));
                    var roll = Math.random() * 1;
                    var odds2 = 1/(1+10**((-(this.matches[i+1][0][1]-this.matches[i+1][1][1]))*30.464/400));
                    var roll2 = Math.random() * 1;
                    if(roll<odds){
                        var win = 0
                    }
                    else{
                        var win = 1
                    }
                    if(roll2<odds2){
                        var win2 = 0
                    }
                    else{
                        var win2 = 1
                    }
                    hold.push(this.matches[i][win],this.matches[i+1][win2]);
                    this.round2.push(hold)
                    if(win==0){
                        this.matches[i][0][2]++;
                    }
                    else{
                        this.matches[i][1][2]++;
                    }
                    if(win2==0){
                        this.matches[i+1][0][2]++;
                    }
                    else{
                        this.matches[i+1][1][2]++;
                    }
                    
                }
                console.log(this.round2)
            },
            simSecondRound(){
                console.log("second")
                for(var i =0; i < 16; i=i+2){
                    var hold = [];
                    var odds = 1/(1+10**((-(this.round2[i][0][1]-this.round2[i][1][1]))*30.464/400));
                    var roll = Math.random() * 1;
                    var odds2 = 1/(1+10**((-(this.round2[i+1][0][1]-this.round2[i+1][1][1]))*30.464/400));
                    var roll2 = Math.random() * 1;
                    if(roll<odds){
                        var win = 0
                    }
                    else{
                        var win = 1
                    }
                    if(roll2<odds2){
                        var win2 = 0
                    }
                    else{
                        var win2 = 1
                    }
                    hold.push(this.round2[i][win],this.round2[i+1][win2]);
                    this.round3.push(hold)
                    if(win==0){
                        this.round2[i][0][2]++;
                    }
                    else{
                        this.round2[i][1][2]++;
                    }
                    if(win2==0){
                        this.round2[i+1][0][2]++;
                    }
                    else{
                        this.round2[i+1][1][2]++;
                    }
                }
                console.log(this.round3) 
            },
            simThirdRound(){
                console.log("third")
                for(var i =0; i < 8; i=i+2){
                    var hold = [];
                    var odds = 1/(1+10**((-(this.round3[i][0][1]-this.round3[i][1][1]))*30.464/400));
                    var roll = Math.random() * 1;
                    var odds2 = 1/(1+10**((-(this.round3[i+1][0][1]-this.round3[i+1][1][1]))*30.464/400));
                    var roll2 = Math.random() * 1;
                    if(roll<odds){
                        var win = 0
                    }
                    else{
                        var win = 1
                    }
                    if(roll2<odds2){
                        var win2 = 0
                    }
                    else{
                        var win2 = 1
                    }
                    hold.push(this.round3[i][win],this.round3[i+1][win2]);
                    this.round4.push(hold)
                    if(win==0){
                        this.round3[i][0][2]++;
                    }
                    else{
                        this.round3[i][1][2]++;
                    }
                    if(win2==0){
                        this.round3[i+1][0][2]++;
                    }
                    else{
                        this.round3[i+1][1][2]++;
                    }
                }
                console.log(this.round4) 
            },
            simFourthRound(){
                console.log("fourth")
                for(var i =0; i < 4; i=i+2){
                    var hold = [];
                    var odds = 1/(1+10**((-(this.round4[i][0][1]-this.round4[i][1][1]))*30.464/400));
                    var roll = Math.random() * 1;
                    var odds2 = 1/(1+10**((-(this.round4[i+1][0][1]-this.round4[i+1][1][1]))*30.464/400));
                    var roll2 = Math.random() * 1;
                    if(roll<odds){
                        var win = 0
                    }
                    else{
                        var win = 1
                    }
                    if(roll2<odds2){
                        var win2 = 0
                    }
                    else{
                        var win2 = 1
                    }
                    hold.push(this.round4[i][win],this.round4[i+1][win2]);
                    this.round5.push(hold)
                    if(win==0){
                        this.round4[i][0][2]++;
                    }
                    else{
                        this.round4[i][1][2]++;
                    }
                    if(win2==0){
                        this.round4[i+1][0][2]++;
                    }
                    else{
                        this.round4[i+1][1][2]++;
                    }
                }
                console.log(this.round5) 
            },
            simFifthRound(){
                console.log("fifth")
                 var hold = [];
                var odds = 1/(1+10**((-(this.round5[0][0][1]-this.round5[0][1][1]))*30.464/400));
                var roll = Math.random() * 1;
                var odds2 = 1/(1+10**((-(this.round5[1][0][1]-this.round5[1][1][1]))*30.464/400));
                var roll2 = Math.random() * 1;
                if(roll<odds){
                    var win = 0
                }
                else{
                    var win = 1
                }
                if(roll2<odds2){
                    var win2 = 0
                }
                else{
                    var win2 = 1
                }
                hold.push(this.round5[0][win],this.round5[1][win2]);
                this.round6.push(hold)
                if(win==0){
                    this.round5[0][0][2]++;
                }
                else{
                    this.round5[0][1][2]++;
                }
                if(win2==0){
                    this.round5[1][0][2]++;
                }
                else{
                    this.round5[1][1][2]++;
                }
                console.log(this.round6) 
            },
            simSixRound(){
                console.log("six")
                var hold = [];
                var odds = 1/(1+10**((-(this.round5[0][0][1]-this.round5[0][1][1]))*30.464/400));
                var roll = Math.random() * 1;
                if(roll<odds){
                    var win = 0
                }
                else{
                    var win = 1
                }
                if(win==0){
                    this.round6[0][0][2]++;
                }
                else{
                    this.round6[0][1][2]++;
                }
            },
            revealRound(){
                console.log("reveal")
                this.roundCount++;
                var round = this.roundCount;
                if(round>=1){
                    this.played1 = true;
                    this.show2 = true;
                }
                if(round>=2){
                    this.played2 = true;
                    this.show3 = true;
                }
                if(round>=3){
                    this.played3 = true;
                    this.show4 = true;
                }
                if(round>=4){
                    this.played4 = true;
                    this.show5 = true;
                }
                if(round>=5){
                    this.played5 = true;
                    this.show6 = true;
                }
                if(round>=6){
                    this.played6 = true;
                }

            },
            restore(){
                this.teams=[
                    ["Duke",96.3,0,1,false],
                    ["North Dakota State",70.35,0,16,false],
                    ["Virginia Commonwealth",82.23,0,8,false],
                    ["Central Florida",81.72,0,9,false],
                    ["Mississippi State",86.44,0,5,false],
                    ["Liberty",78.01,0,12,false],
                    ["Virginia Tech",88.74,0,4,false],
                    ["Saint Louis",77.35,0,13,false],
                    ["Maryland",84.84,0,6,false],
                    ["Belmont",81.06,0,11,false],
                    ["Louisiana State",86.41,0,3,false],
                    ["Yale",76.89,0,14,false],
                    ["Louisville",85.9,0,7,false],
                    ["Minnesota",81.19,0,10,false],
                    ["Michigan State",92.19,0,2,false],
                    ["Bradley",72.91,0,15,false],
                    ["Gonzaga",95,0,1,false],
                    ["Fairleigh Dickinson",70.04,0,16,false],
                    ["Syracuse",83.92,0,8,false],
                    ["Baylor",82.71,0,9,false],
                    ["Marquette",85.31,0,5,false],
                    ["Murray State",81.29,0,12,false],
                    ["Florida State",88.39,0,4,false],
                    ["Vermont",79.29,0,13,false],
                    ["Buffalo",85.75,0,6,false],
                    ["Arizona State",80.87,0,11,false],
                    ["Texas Tech",89.65,0,3,false],
                    ["Northern Kentucky",77.25,0,14,false],
                    ["Nevada",86.12,0,7,false],
                    ["Florida",83.95,0,10,false],
                    ["Michigan",91.13,0,2,false],
                    ["Montana",76.19,0,15,false],
                    ["Virginia",95.2,0,1,false],
                    ["Gardner-Webb",71.75,0,16,false],
                    ["Mississippi",81.64,0,8,false],
                    ["Oklahoma",83.01,0,9,false],
                    ["Wisconsin",86.7,0,5,false],
                    ["Oregon",84.02,0,12,false],
                    ["Kansas State",86.66,0,4,false],
                    ["UC-Irvine",78.35,0,13,false],
                    ["Villanova",86.95,0,6,false],
                    ["Saint Mary's (CA)",83.58,0,11,false],
                    ["Purdue",89.09,0,3,false],
                    ["Old Dominion",77.07,0,14,false],
                    ["Cincinnati",85.12,0,7,false],
                    ["Iowa",82.4,0,10,false],
                    ["Tennessee",91.65,0,2,false],
                    ["Colgate",74.95,0,15,false],
                    ["North Carolina",93.25,0,1,false],
                    ["Iona",71.86,0,16,false],
                    ["Utah State",82.28,0,8,false],
                    ["Washington",82.55,0,9,false],
                    ["Auburn",88.65,0,5,false],
                    ["New Mexico State",80.91,0,12,false],
                    ["Kansas",86.3,0,4,false],
                    ["Northeastern",78.58,0,13,false],
                    ["Iowa State",86.16,0,6,false],
                    ["Ohio State",82.59,0,11,false],
                    ["Houston",88.13,0,3,false],
                    ["Georgia State",76.13,0,14,false],
                    ["Wofford",84.38,0,7,false],
                    ["Seton Hall",82.18,0,10,false],
                    ["Kentucky",91.24,0,2,false],
                    ["Abilene Christian",72.33,0,15,false]
                ];
                this.matches=[];
                this.round2=[];
                this.round3=[];
                this.round4=[];
                this.round5=[];
                this.round6=[];
                this.played1=false;
                this.played2=false;
                this.played3=false;
                this.played4=false;
                this.played5=false;
                this.played6=false;
                this.show2=false;
                this.show3=false;
                this.show4=false;
                this.show5=false;
                this.show6=false;
                this.roundCount=0;
            },
            revealAll(){
                this.restore();
                this.roundCount = 7;
                this.test();
                this.simFirstRound();
                this.simSecondRound();
                this.simThirdRound();
                this.simFourthRound();
                this.simFifthRound();
                this.simSixRound();
                this.revealRound();
            },
            reset(){
                this.restore();
                this.test();
                this.simFirstRound();
                this.simSecondRound();
                this.simThirdRound();
                this.simFourthRound();
                this.simFifthRound();
                this.simSixRound();
            }
        },
        beforeMount:function(){
            console.log("TEST")
            this.test();
            this.simFirstRound();
            this.simSecondRound();
            this.simThirdRound();
            this.simFourthRound();
            this.simFifthRound();
            this.simSixRound();
        }
    }
    
</script>

<style scoped>
.match{
    border: 1px solid #444;
    padding: 0;
    border-left: 0px;
    height: 40px;
    font-size: 12px;
    margin-top:10px;
    text-align: left;
    white-space: nowrap;
}
.right .match{
    border: 1px solid #444 !important;
    border-right: 0px !important;
}
.slot{
    margin-bottom: 5px;
    width: 100%;
    max-height: 20px;
    white-space: nowrap;
    overflow: hidden;
}
.score{
    float: right;
    padding-right:2px;
}
.mycol-1{
    width:12%;
    padding:15px;
}
.center-seperator{
    width:40px;
}
.round-2-offset{
    height:20px;
}
.round-3-offset{
    height:45px;
}
.round-4-offset{
    height:90px;
}
.match.round2{
    height:50px;
    margin-bottom:50px;
}
.match.round3{
    height:100px;
    margin-bottom:100px;
}
.match.round4{
    height:200px;
    margin-bottom:100px;
}
.spacer-2{
    height:10px;
    width:1px;
}
.spacer-3{
    height:60px;
    width:1px;
}
.spacer-4{
    height:160px;
    width:1px;
}
.round-1-right{
    float:right;
}
.right.col-2{
    padding: 0px;
}
.final-four-match{
    margin-bottom:50px !important;
}
.championship{
    border: 0.5px solid #444;
}
.champ-top{
    height:55px;
    font-size: 12px;
}
.champ-bottom{
    font-size: 12px;
}
.win.played{
    font-weight: bold;
    color:lightskyblue;
}
.lose.played{
    text-decoration: line-through;
}
.lose.played span{
    text-decoration: line-through;
}
.hideslot{
    visibility: hidden;
}
.teamhover{
    transition: transform .2s;
    transform: scale(1.5);
    color:red;
}

</style>
