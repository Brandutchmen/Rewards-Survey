<template>
  <v-container fluid>
    <v-row class="text-center mt-4 mb-4">
      <v-spacer></v-spacer>
      <v-stepper v-model="e1">
        <v-stepper-header>
          <v-stepper-step :complete="e1 > 3" :step="e1 > 3 ? '1' : e1 ">Verify Identity</v-stepper-step>

          <v-divider></v-divider>

          <v-stepper-step :complete="e1 > 14" :step="e1 > 14 ? '4' : e1 ">Answer Survey Questions</v-stepper-step>

          <v-divider></v-divider>

          <v-stepper-step step="15">Get $50 Walmart Gift Card</v-stepper-step>
        </v-stepper-header>

        <v-stepper-items>
          <v-stepper-content step="1">
            <h2 class="font-weight-medium">What is your name?</h2>
            <v-text-field :rules="required" autofocus class="mx-12 mb-6" placeholder="John Doe"></v-text-field>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
          </v-stepper-content>

          <v-stepper-content step="2">
            <h2 class="font-weight-medium">What is your zip code?</h2>
            <v-text-field :rules="required" autofocus class="mx-12 mb-6" placeholder="12345"></v-text-field>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="3">
            <h2 class="font-weight-medium">What country do you live in?</h2>
            <v-select
                    class="mx-12 mb-6"
                    :items="countries"
                    label="Countries"
            ></v-select>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="4">
            <h2 class="font-weight-medium">Do you want to receive a $50 Walmart Gift Card?</h2>
            <v-col align-self="center">
            <v-radio-group>
              <v-radio
                      label="Yes"
              ></v-radio>
              <v-radio
                      label="No"
              ></v-radio>
            </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="5">
            <h2 class="font-weight-medium">What car brand would you purchase from?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Ford"
                ></v-radio>
                <v-radio
                        label="Volvo"
                ></v-radio>
                <v-radio
                        label="Ferrari"
                ></v-radio>
                <v-radio
                        label="Volkswagen"
                ></v-radio>
                <v-radio
                        label="Chevrolet"
                ></v-radio>
                <v-radio
                        label="Buick"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="6">
            <h2 class="font-weight-medium">Do you use online banking?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Yes"
                ></v-radio>
                <v-radio
                        label="No"
                ></v-radio>
                <v-radio
                        label="Maybe"
                ></v-radio>
                <v-radio
                        label="Probably"
                ></v-radio>
                <v-radio
                        label="I am not sure"
                ></v-radio>
                <v-radio
                        label="I would like to speak to a professional about this"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="7">
            <h2 class="font-weight-medium">Do you use Apple or Samsung?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Apple"
                ></v-radio>
                <v-radio
                        label="Samsung"
                ></v-radio>
                <v-radio
                        label="Other"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="8">
            <h2 class="font-weight-medium">Have you ever used Teamviewer or Anydesk?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Yes"
                ></v-radio>
                <v-radio
                        label="No"
                ></v-radio>
                <v-radio
                        label="Prefer not to say"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="9">
            <h2 class="font-weight-medium">Have you purchased WinRar in the past 30 years?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Yes"
                ></v-radio>
                <v-radio
                        label="No"
                ></v-radio>
                <v-radio
                        label="My license expired"
                ></v-radio>
                <v-radio
                        label="Prefer not to say"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="10">
            <h2 class="font-weight-medium">What is your spirit animal?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Eagle"
                ></v-radio>
                <v-radio
                        label="Fox"
                ></v-radio>
                <v-radio
                        label="Lion"
                ></v-radio>
                <v-radio
                        label="Bear"
                ></v-radio>
                <v-radio
                        label="Tuna"
                ></v-radio>
                <v-radio
                        label="Prefer not to say"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="11">
            <h2 class="font-weight-medium">What drink do you prefer?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Pepsi"
                ></v-radio>
                <v-radio
                        label="Coke"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="12">
            <h2 class="font-weight-medium">Which of the following are you?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Introvert"
                ></v-radio>
                <v-radio
                        label="Extrovert"
                ></v-radio>
                <v-radio
                        label="Prefer not to answer"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="13">
            <h2 class="font-weight-medium">Are you vegan?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Yes"
                ></v-radio>
                <v-radio
                        label="No"
                ></v-radio>
                <v-radio
                        label="Prefer not to answer"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="14">
            <h2 class="font-weight-medium">Which celebrity would you like to meet?</h2>
            <v-col align-self="center">
              <v-radio-group>
                <v-radio
                        label="Tom Cruise"
                ></v-radio>
                <v-radio
                        label="Indiana Jones"
                ></v-radio>
                <v-radio
                        label="Chris Pratt"
                ></v-radio>
                <v-radio
                        label="Tom Holland"
                ></v-radio>
                <v-radio
                        label="Scarlett Johansson"
                ></v-radio>
                <v-radio
                        label="Boris Johnson"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-btn
                    color="primary"
                    @click="nextQuestion"
            >
              Continue
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>

          <v-stepper-content step="15">
            <h2 class="font-weight-medium">Thank you for filling out our survey!</h2>
            <h2 class="font-weight-medium">Which email address should we mail the gift card to?</h2>
            <v-text-field :rules="email" class="mx-12 mb-6" placeholder="john@example.com"></v-text-field>
            <v-btn
                    color="primary"
                    @click="e1 = 1"
            >
              Take the survey again!
            </v-btn>
            <v-btn text @click="previousQuestion">Back</v-btn>
          </v-stepper-content>


        </v-stepper-items>
      </v-stepper>
      <v-spacer></v-spacer>

    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data () {
      return {
        e1: 1,
        required: [
          value => !!value || 'Required.',
        ],
        email: [
          value => !!value || 'Required.',
          value => {
            const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return pattern.test(value) || 'Invalid e-mail.'
          },
        ],
        countries: ['United States', 'Canada', 'Mexico', 'Alaska'],
      }
    },
    methods: {
        nextQuestion() {
          this.e1 = this.e1 + 1;
        },

        previousQuestion() {
          this.e1 = this.e1 - 1;
        }
    }
  }
</script>
