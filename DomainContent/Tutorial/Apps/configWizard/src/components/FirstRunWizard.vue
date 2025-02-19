<!--
//
//  FirstRunWizard.vue
//
//  Created by Kalila L. on Feb 3 2021
//  Copyright 2021 Vircadia contributors.
//
//  Distributed under the Apache License, Version 2.0.
//  See the accompanying file LICENSE or http://www.apache.org/licenses/LICENSE-2.0.html
//
-->

<template>
    <v-stepper v-model="stepperModel">
        <v-stepper-header>
            <v-stepper-step
                :complete="stepperModel > 1"
                step="1"
            >
                Welcome!
            </v-stepper-step>
                
            <v-divider></v-divider>
                
            <v-stepper-step
                :complete="stepperModel > 2"
                step="2"
            >
                Quality
            </v-stepper-step>
            
            <v-divider></v-divider>
                
            <v-stepper-step
                :complete="stepperModel > 3"
                step="3"
            >
                Performance
            </v-stepper-step>
            
            <v-divider></v-divider>
            
            <v-stepper-step
                :complete="stepperModel > 4"
                step="4"
            >
                Nickname
            </v-stepper-step>
            
            <v-divider></v-divider>
                
            <v-stepper-step
                :complete="stepperModel > 5"
                step="5"
            >
                Ready!
            </v-stepper-step>
        </v-stepper-header>

        <v-stepper-items>
            <v-stepper-content step="1">
                <v-card>
                    <v-img
                        height="80px"
                        src="/assets/1920_bar.png"
                    >
                        <v-card-title
                            class="text-h3 font-weight-light"
                        >
                            Welcome to Vircadia!
                        </v-card-title>
                    </v-img>
                    
                    <v-card-subtitle
                        class="text-h5 font-weight-light"
                    >
                        Let's get you setup to experience the virtual world. <br/>
                        First, we need to select some performance and graphics quality options. <br/><br/>
                        Press <b style="color: white;">Continue</b> when you are ready.
                    </v-card-subtitle>
                    
                    <v-divider></v-divider>
                    
                    <v-card-actions>
                        <v-spacer></v-spacer>   
                        <v-btn
                            color="primary"
                            @click="stepperModel++"
                            x-large
                        >
                            Continue
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-stepper-content>

            <v-stepper-content step="2">
                <v-card>
                    <v-img
                        height="80px"
                        src="/assets/1920_bar.png"
                    >
                        <v-card-title
                            class="text-h3 font-weight-light"
                        >
                            Quality
                        </v-card-title>
                    </v-img>
                    
                    <v-card-text>
                        <v-radio-group
                            v-model="performancePreset"
                        >
                            <template v-slot:label>
                                <div class="text-h5 font-weight-light mb-5">
                                    What level of visual quality would you like?<br/>
                                    <b>Remember! If you do not have a powerful computer, you may want to set this to low or medium at most.</b>
                                </div>
                            </template>
                            
                            <v-radio :value="performancePresetValues[0]">
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="green--text">Low Quality</strong> Average Laptop / Slow Computer</div>
                                </template>
                            </v-radio>
                            <v-radio :value="performancePresetValues[1]">
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="blue--text">Medium Quality</strong> Average Computer - <b><i>Recommended</i></b></div>
                                </template>
                            </v-radio>
                            <v-radio :value="performancePresetValues[2]">
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="red--text">High Quality</strong> Gaming Computer</div>
                                </template>
                            </v-radio>
                        </v-radio-group>
                    </v-card-text>

                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-btn
                            color="primary"
                            @click="stepperModel--"
                            x-large
                        >
                            Back
                        </v-btn>
                        <v-spacer></v-spacer>   
                        <v-btn
                            color="primary"
                            @click="stepperModel++"
                            x-large
                        >
                            Continue
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-stepper-content>

            <v-stepper-content step="3">
                <v-card>
                    <v-img
                        height="80px"
                        src="/assets/1920_bar.png"
                    >
                        <v-card-title
                            class="text-h3 font-weight-light"
                        >
                            Performance
                        </v-card-title>
                    </v-img>
                    
                    <v-card-text>
                        <v-radio-group 
                            v-model="refreshRateProfile"
                        >
                            <template v-slot:label>
                                <div class="text-h5 font-weight-light mb-5">
                                    Do you want a smooth experience <i>(high refresh rate)</i> or do you want to conserve power and resources <i>(low refresh rate)</i> on your computer?
                                    <br/><b><i class="text-h6">Note: This does not apply to virtual reality headsets.</i></b>
                                </div>
                            </template>
                            <v-radio>
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="green--text">Not Smooth (20 Hz)</strong> Conserve Power</div>
                                </template>
                            </v-radio>
                            <v-radio>
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="blue--text">Smooth (30 Hz)</strong> Use Average Resources</div>
                                </template>
                            </v-radio>
                            <v-radio>
                                <template v-slot:label>
                                    <div class="text-h5"><strong class="red--text">Very Smooth (60 Hz)</strong> Use Maximum Resources - <b><i>Recommended</i></b></div>
                                </template>
                            </v-radio>
                        </v-radio-group>
                    </v-card-text>
                    
                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-btn
                            color="primary"
                            @click="stepperModel--"
                            x-large
                        >
                            Back
                        </v-btn>
                        <v-spacer></v-spacer>   
                        <v-btn
                            color="primary"
                            @click="stepperModel++"
                            x-large
                        >
                            Continue
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-stepper-content>
            
            <v-stepper-content step="4">
                <v-card>
                    <v-img
                        height="80px"
                        src="/assets/1920_bar.png"
                    >
                        <v-card-title
                            class="text-h3 font-weight-light"
                        >
                            Display Name
                        </v-card-title>
                    </v-img>
                    
                    <v-card-text>
                        <div class="text-h5 font-weight-light mb-5">
                            What should people call you?<br/>
                            This is simply a nickname, it will be shown in place of your username (if you have one).
                        </div>

                        <v-text-field
                            label="Display Name"
                            v-model="displayName"
                            placeholder="Don't be shy!"
                        ></v-text-field>
                    </v-card-text>
                    
                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-btn
                            color="primary"
                            @click="stepperModel--"
                            x-large
                        >
                            Back
                        </v-btn>
                        <v-spacer></v-spacer>   
                        <v-btn
                            color="primary"
                            @click="stepperModel++"
                            x-large
                        >
                            Continue
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-stepper-content>
            
            <v-stepper-content step="5">
                <v-card>
                    <v-img
                        height="80px"
                        src="/assets/1920_bar.png"
                    >
                        <v-card-title
                            class="text-h3 font-weight-light"
                        >
                            All done!
                        </v-card-title>
                    </v-img>
                    
                    <v-card-subtitle
                        class="text-h5 font-weight-light"
                    >
                        Now you're ready to go!<br/>
                        Take a look at the controls reference after completing this wizard.<br/>
                        Press <b style="color: white;">Complete</b> when you are ready. 
                    </v-card-subtitle>
                    
                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-btn
                            color="primary"
                            @click="stepperModel--"
                            x-large
                        >
                            Back
                        </v-btn>
                        <v-spacer></v-spacer>   
                        <v-btn
                            color="green"
                            @click="completeWizard"
                            x-large
                        >
                            Complete
                        </v-btn>
                    </v-card-actions>
                </v-card>
            </v-stepper-content>
        </v-stepper-items>
    </v-stepper>
</template>

<script>
var vue_this;

function browserDevelopment() {
    if (typeof EventBridge !== 'undefined') {
        return false; // We are in Vircadia.
    } else {
        return true; // We are in the browser, probably for development purposes.
    }
}

if (!browserDevelopment()) {
    // eslint-disable-next-line
    EventBridge.scriptEventReceived.connect(function (receivedCommand) {
        receivedCommand = JSON.parse(receivedCommand);
        
        // We route the data based on the command given.
        if (receivedCommand.command === 'script-to-web-initialize') {
            vue_this.initialize(receivedCommand.data);
        }
    });
}

export default {
    name: 'FirstRunWizard',
    
    data: () => ({
        stepperModel: 1,
        performancePreset: 0,
        performancePresetValues: [
            1, // Low
            2, // Med
            3 // High
        ],
        refreshRateProfile: 0, // Low, 20 fps
        displayName: ''
    }),
    
    methods: {
        initialize: function (data) {
            this.performancePreset = data.performancePreset;
            this.refreshRateProfile = data.refreshRateProfile;
            this.displayName = data.displayName;
        },
        completeWizard: function () {
            var objectToSend = {
                'command': 'complete-wizard',
                'data': {
                    'performancePreset': this.performancePreset,
                    'refreshRateProfile': this.refreshRateProfile,
                    'displayName': this.displayName
                }
            }

            this.sendMessageToScript(objectToSend);
        },
        sendMessageToScript: function (commandAndData) {
            this.$emit('send-message-to-script', commandAndData);
        }
    },
    
    created: function () {
        vue_this = this;
        
        this.sendMessageToScript({
            'command': 'first-run-wizard-ready',
            'data': ''
        });
    }
}
</script>
