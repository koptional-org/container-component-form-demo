<template>
  <div class="text-center">
    <form @submit.prevent="$emit('submit', formModel)">
      <div class="px-2 py-2 text-left grid grid-cols-1 sm:grid-cols-2 gap-2">
        <div class="px-2">
          <label>
            First name
            <input
              v-model="formModel.first"
              type="text"
              name="first"
              class="
                px-2
                py-1
                text-gray-600
                border border-gray-200
                rounded-md
                w-full
                outline-none
                focus:outline-none
                focus:border-none
                focus:ring-1
                focus:ring-blue-500
              "
              required
            />
          </label>
        </div>
        <div class="px-2">
          <label>
            Last name
            <input
              v-model="formModel.last"
              type="text"
              name="last"
              class="
                px-2
                py-1
                text-gray-600
                border border-gray-200
                rounded-md
                w-full
                outline-none
                focus:outline-none
                focus:border-none
                focus:ring-1
                focus:ring-blue-500
              "
              required
            />
          </label>
        </div>
      </div>
      <div class="px-4 py-2 text-left">
        <label>
          Email
          <input
            v-model="formModel.email"
            type="text"
            name="email"
            class="
              px-2
              py-1
              text-gray-600
              border border-gray-200
              rounded-md
              w-full
              outline-none
              focus:outline-none
              focus:border-none
              focus:ring-1
              focus:ring-blue-500
            "
            required
          />
        </label>
        <small class="text-xs text-gray-500"
          >We'll never validate your email</small
        >
      </div>
      <div class="px-2 py-2 text-left grid grid-cols-1 sm:grid-cols-2 gap-2">
        <div class="px-2">
          <label>
            City
            <input
              v-model="formModel.city"
              type="text"
              name="city"
              class="
                px-2
                py-1
                text-gray-600
                border border-gray-200
                rounded-md
                w-full
                outline-none
                focus:outline-none
                focus:border-none
                focus:ring-1
                focus:ring-blue-500
              "
              required
            />
          </label>
        </div>
        <div class="px-2">
          <label>
            State
            <select
              class="
                px-2
                py-1
                bg-white
                text-gray-600
                border border-gray-200
                w-full
                outline-none
                focus:outline-none
                focus:border-none
                focus:ring-1
                focus:ring-blue-500
              "
              required
            >
              <option
                v-for="(option, index) in stateOptions"
                :key="index"
                :value="option.value"
              >
                {{ option.text }}
              </option>
            </select>
          </label>
        </div>
      </div>
      <div class="text-center py-2">
        <button
          type="submit"
          class="
            px-2
            py-2
            bg-indigo-600
            text-white
            font-medium
            rounded-md
            hover:bg-indigo-800
          "
        >
          Submit
        </button>
      </div>
    </form>
  </div>
</template>
<script>
import map from 'lodash/map'
import { stateCodes } from '@/store/constants'
export default {
  data() {
    return {
      formModel: {
        first: null,
        last: null,
      },
    }
  },
  computed: {
    /**
     * @returns {{text: string; value: string | null; disabled?: boolean;}[]}
     */
    stateOptions() {
      return [
        {
          text: 'Select one...',
          disabled: true,
          value: null,
        },
      ].concat(
        map(stateCodes, (state, stateCode) => ({
          value: state,
          text: stateCode,
        }))
      )
    },
  },
}
</script>
