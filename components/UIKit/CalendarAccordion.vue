<template>
  <div class="calendar-accordion"
    :class="{'calendar-accordion--open' : open}"
  >
    <div class="calendar-accordion__head"
      @click="open = !open"
    >
      <calendar class="calendar-accordion__head-icon" />
      <span class="timemaster-subtitle">Choose date</span>
    </div>

    <div class="calendar-accordion__body">
      <div class="calendar-accordion__data">
        <arrow-prev class="calendar-accordion__data-prev" />
        <span class="timemaster-subtitle">April, 2022</span>
        <arrow-next class="calendar-accordion__data-next" />
      </div>
      <ol class="calendar-accordion__grid">
        <li class="calendar-accordion__week-day">ПН</li>
        <li class="calendar-accordion__week-day">ВТ</li>
        <li class="calendar-accordion__week-day">СР</li>
        <li class="calendar-accordion__week-day">ЧТ</li>
        <li class="calendar-accordion__week-day">ПТ</li>
        <li class="calendar-accordion__week-day">СБ</li>
        <li class="calendar-accordion__week-day">ВС</li>

        <li class="calendar-accordion__date out">28</li>
        <li class="calendar-accordion__date out">29</li>
        <li class="calendar-accordion__date out">30</li>
        <li class="calendar-accordion__date">01</li>
        <li class="calendar-accordion__date">02</li>
        <li class="calendar-accordion__date">03</li>
        <li class="calendar-accordion__date">04</li>
        <li class="calendar-accordion__date">05</li>
        <li class="calendar-accordion__date selected">06</li>
        <li class="calendar-accordion__date">07</li>
        <li class="calendar-accordion__date">08</li>
        <li class="calendar-accordion__date">09</li>
        <li class="calendar-accordion__date current">10</li>
        <li class="calendar-accordion__date">11</li>
        <li class="calendar-accordion__date">12</li>
        <li class="calendar-accordion__date">13</li>
        <li class="calendar-accordion__date">14</li>
        <li class="calendar-accordion__date">15</li>
        <li class="calendar-accordion__date">16</li>
        <li class="calendar-accordion__date">17</li>
        <li class="calendar-accordion__date">18</li>
        <li class="calendar-accordion__date">19</li>
        <li class="calendar-accordion__date">20</li>
        <li class="calendar-accordion__date">21</li>
        <li class="calendar-accordion__date">22</li>
        <li class="calendar-accordion__date">23</li>
        <li class="calendar-accordion__date">24</li>
        <li class="calendar-accordion__date">25</li>
        <li class="calendar-accordion__date">26</li>
        <li class="calendar-accordion__date">27</li>
        <li class="calendar-accordion__date">28</li>
        <li class="calendar-accordion__date">29</li>
        <li class="calendar-accordion__date">30</li>
        <li class="calendar-accordion__date">31</li>
        <li class="calendar-accordion__date out">01</li>

      </ol>
    </div>
  </div>
</template>

<script>
import calendar from '../icons/calendar.vue';
import arrowPrev from '../icons/arrowPrev.vue';
import arrowNext from '../icons/arrowNext.vue';

export default {
  name: "CalendarAccordion",
  components: {calendar, arrowPrev, arrowNext},
  data: () => ({
    open: false
  })
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .calendar-accordion {
    width: 300rem;
    margin: 0 auto;
    overflow: hidden;
    background: #ffffff;
    border-radius: 30rem;
    box-shadow: 0px 4px 4px rgba($black, 0.25);
    &__head {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10rem;
      padding: 20rem 0;

      span {
        color: $gray;
      }
      &-icon {
        display: grid;
        place-content: center;
      }
    }
    &__body {
      height: 0;
      transition: height 360ms ease-in-out;
      border-top: 1px solid rgba($gray, 0.5);
    }
    &__data {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20rem 14rem 9rem;
      span {
        color: $main-color;
        letter-spacing: unset;
      }
      &-prev,
      &-next {
        display: grid;
        place-content: center;
      }
    }
    &__grid {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      gap: 18rem;
      padding: 12rem;
      place-items: center;
    }
    &__week-day {
      font-size: 10rem;
      line-height: 12.5rem;
      color: $gray;

      &:nth-child(6),
      &:nth-child(7) {
        color: #DE2424;
      }
    }
    &__date {
      width: 100%;
      height: 100%;
      display: grid;
      place-content: center;
      border-radius: 5rem;
      transition: all 360ms ease-in-out;

      &.out {
        color: $gray;
      }
      &.current {
        background-color: $main-color;
        color: $white;
      }
      &.selected {
        border: 1px solid $main-color;
      }
    }


    &--open {
      .calendar-accordion__body {
        height: 303rem;
      }
    }
  }
</style>
