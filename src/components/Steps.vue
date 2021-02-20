<template>
  <div :class="{'steps': true, ...classNames }">
    <div class="step__item" v-for="(step, index) in steps" :key="index">
      <div :class="`step__item__number ${step.selected ? 'step__item__number--selected' : ''}`">
        {{ step.step }}
      </div>

      <div :class="`step__item__text ${step.selected ? 'step__item__text--selected' : ''}`">
        {{ step.text }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Steps',

  props: {
    classNames: {
      type: Object,
      default: () => {},
    },
  },

  data() {
    return {
      steps: [
        {
          step: 1,
          selected: true,
          text: 'Beantwoord de vragen'
        },
        {
          step: 2,
          selected: false,
          text: 'Vul je gegevens in'
        },
        {
          step: 3,
          selected: false,
          text: 'Heb je gewonnen?'
        }
      ]
    };
  }
}
</script>

<style scoped>
.steps {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 14px 18px;
  background: lightcyan;
}

.step__item {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.step__item__number {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: #fff;
  color: #2B58BF;
  font-size: 13px;
  font-weight: 500;
  margin-bottom: 8px;
}

.step__item__number--selected {
  background: rgb(53,130,234);
  background: linear-gradient(177deg, rgba(53,130,234,1) 0%, rgba(76,85,195,1) 100%);
  color: #fff;
}

.step__item__text {
  font-size: 13px;
  color: #000;
  text-align: center;
  font-weight: 500;
}

.step__item__text--selected {
  color: #3F6CD7;
}

/* when component has _is_transparent */
._is_transparent {
  background: transparent;
  border-bottom: 1px solid rgba(255, 255, 255, .4);
  margin-bottom: 16px;
}

._is_transparent .step__item__text {
  color: #fff;
}

._is_transparent .step__item__number {
  border: 2px solid #fff;
}
</style>
