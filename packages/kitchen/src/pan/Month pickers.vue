<template>
  <v-container>
    <v-btn
      large
      color="red"
      dark
      fab
      fixed
      bottom
      right
      @click="() => landscape = !landscape"
    >
      <v-icon small>
        {{ landscape ? 'mdi-phone-rotate-portrait' : 'mdi-phone-rotate-landscape' }}
      </v-icon>
    </v-btn>

    <v-layout column>
      <main-header>Month pickers</main-header>

      <core-title>
        Month pickers
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            type="month"
          />
        </v-layout>
      </core-section>

      <core-title>
        Landscape
      </core-title>
      <core-section center>
        <v-date-picker
          v-model="model"
          type="month"
          landscape
        />
      </core-section>

      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-flex text-center>
            <core-title>
              Readonly
            </core-title>
            <v-date-picker
              v-model="model"
              type="month"
              :landscape="landscape"
              readonly
            />
          </v-flex>
          <v-flex text-center>
            <core-title>
              Disabled
            </core-title>
            <v-date-picker
              v-model="model"
              type="month"
              :landscape="landscape"
              disabled
            />
          </v-flex>
          <v-flex text-center>
            <core-title>
              Reactive
            </core-title>
            <v-date-picker
              v-model="model"
              type="month"
              :landscape="landscape"
              reactive
            />
          </v-flex>
        </v-layout>
      </core-section>

      <core-title>
        Color
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="success"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="red lighten-2"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="blue"
          />
        </v-layout>
      </core-section>

      <core-title>
        Header colors
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            header-color="success"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            header-color="red lighten-2"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            header-color="blue"
          />
        </v-layout>
      </core-section>

      <core-title>
        Using header colors with colors
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="red lighten-2"
            header-color="success"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="error"
            header-color="red lighten-2"
          />
          <v-date-picker
            v-model="model"
            type="month"
            :landscape="landscape"
            class="mt-6"
            color="teal"
            header-color="blue"
          />
        </v-layout>
      </core-section>

      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-flex text-center>
            <core-title>
              Allowed months: min/max
            </core-title>
            <v-date-picker
              v-model="modelMM"
              type="month"
              :landscape="landscape"
              min="2018-11"
              max="2019-08"
            />
          </v-flex>
          <v-flex text-center>
            <core-title>
              Allowed dates: function
            </core-title>
            <v-date-picker
              v-model="modelMM"
              type="month"
              :landscape="landscape"
              :allowed-dates="val => parseInt(val.split('-')[1], 10) % 2 === 1"
            />
          </v-flex>
        </v-layout>
      </core-section>

      <core-title>
        Multiple
      </core-title>
      <core-section>
        <v-layout
          column
          align-center
        >
          <v-date-picker
            v-model="months"
            :landscape="landscape"
            type="month"
            multiple
          />

          <v-combobox
            v-model="months"
            multiple
            chips
            small-chips
            label="Selected months"
            prepend-icon="mdi-calendar"
            readonly
            clearable
          />
        </v-layout>
      </core-section>

      <core-title>
        Custom width
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            class="mt-4"
            type="month"
            width="150"
          />
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            class="mt-4"
            type="month"
            width="290"
          />
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            class="mt-4"
            type="month"
            width="400"
          />
        </v-layout>
      </core-section>

      <core-title>
        Full width
      </core-title>
      <core-section>
        <v-layout
          wrap
          align-center
          justify-space-around
        >
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            class="mt-4"
            full-width
            type="month"
          />
        </v-layout>
      </core-section>

      <core-title>
        Events
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
        >
          <div class="mt-4">
            <div class="subheading text-center">
              Defined by array
            </div>
            <v-date-picker
              v-model="model"
              type="month"
              :landscape="landscape"
              :events="arrayEvents"
              event-color="green lighten-1"
            />
          </div>
          <div class="mt-4">
            <div class="subheading text-center">
              Defined by function
            </div>
            <v-date-picker
              v-model="model"
              type="month"
              :landscape="landscape"
              :event-color="date => date[6] % 2 ? 'red' : 'yellow'"
              :events="functionEvents"
            />
          </div>
        </v-layout>
      </core-section>

      <core-title>
        i18n
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            type="month"
            locale="th"
            class="mt-4"
          />
          <v-date-picker
            v-model="model"
            :landscape="landscape"
            type="month"
            locale="sv-se"
            class="mt-4"
          />
        </v-layout>
      </core-section>

      <core-title>
        Custom icons
      </core-title>
      <core-section center>
        <v-date-picker
          v-model="model"
          :landscape="landscape"
          type="month"
          year-icon="mdi-calendar-blank"
          prev-icon="mdi-skip-previous"
          next-icon="mdi-skip-next"
        />
      </core-section>

      <core-title>
        Current month indicator
      </core-title>
      <core-section>
        <v-layout
          wrap
          justify-space-around
          align-center
        >
          <div class="mt-6">
            <v-date-picker
              v-model="model"
              :landscape="landscape"
              :show-current="false"
              type="month"
            />
          </div>
          <div class="mt-6">
            <v-date-picker
              v-model="model"
              :landscape="landscape"
              type="month"
              show-current="2019-07"
            />
          </div>
        </v-layout>
      </core-section>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    name: 'DatePickers',

    data: () => ({
      arrayEvents: ['2019-01', '2019-03', '2019-06', '2019-12'],
      model: '2019-03',
      modelMM: '2019-03',
      months: ['2019-01', '2019-03', '2020-05', '2020-07'],
      landscape: false,
    }),

    methods: {
      functionEvents (date) {
        const [, month] = date.split('-')
        if ([1, 3, 12].includes(parseInt(month, 10))) return true
        if ([5, 6, 11].includes(parseInt(month, 10))) return ['red', '#00f']
        return false
      },
    },
  }
</script>
