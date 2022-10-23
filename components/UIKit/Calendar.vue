<template>
    <div class="calendar">
      <div class="calendar__data">
        <arrow-prev class="calendar__data-prev" />
        <span class="timemaster-subtitle">April, 2022</span>
        <arrow-next class="calendar__data-next" />
      </div>
      <ol class="calendar__grid">
        <li class="calendar__week-day">ПН</li>
        <li class="calendar__week-day">ВТ</li>
        <li class="calendar__week-day">СР</li>
        <li class="calendar__week-day">ЧТ</li>
        <li class="calendar__week-day">ПТ</li>
        <li class="calendar__week-day">СБ</li>
        <li class="calendar__week-day">ВС</li>

        <li class="calendar__date out">28</li>
        <li class="calendar__date out">29</li>
        <li class="calendar__date out">30</li>
        <li class="calendar__date">01</li>
        <li class="calendar__date">02</li>
        <li class="calendar__date">03</li>
        <li class="calendar__date">04</li>
        <li class="calendar__date">05</li>
        <li class="calendar__date">06</li>
        <li class="calendar__date">07</li>
        <li class="calendar__date ">08</li>
        <li class="calendar__date selected">08</li>
        <li class="calendar__date">09</li>
        <li class="calendar__date current">10</li>
        <li class="calendar__date">11</li>
        <li class="calendar__date">12</li>
        <li class="calendar__date">13</li>
        <li class="calendar__date to-do">14</li>
        <li class="calendar__date">15</li>
        <li class="calendar__date">16</li>
        <li class="calendar__date">17</li>
        <li class="calendar__date">18</li>
        <li class="calendar__date">19</li>
        <li class="calendar__date">20</li>
        <li class="calendar__date">21</li>
        <li class="calendar__date">22</li>
        <li class="calendar__date">23</li>
        <li class="calendar__date">24</li>
        <li class="calendar__date">25</li>
        <li class="calendar__date">26</li>
        <li class="calendar__date">27</li>
        <li class="calendar__date">28</li>
        <li class="calendar__date">29</li>
        <li class="calendar__date">30</li>
        <li class="calendar__date">31</li>
        <li class="calendar__date out">01</li>
      </ol>
    </div>
</template>

<script>
import arrowPrev from '../icons/arrowPrev.vue';
import arrowNext from '../icons/arrowNext.vue';

export default {
  name: "calendar",
  components: {arrowPrev, arrowNext}
}
</script>

<style scoped lang="scss">
  @import "../../static/scss/_vars.scss";

  .calendar {
    border: 1px solid rgba($gray, 0.5);
    border-radius: 30rem;
    &__data {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10rem 14rem;
      border-bottom: 1px solid rgba($gray, 0.5);
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
      gap: 30rem;
      padding: 18rem 13rem;
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
        background-color: $main-color !important;
        color: $white !important;
      }
      &.selected {
        border: 1px solid $main-color;
      }
      &.to-do {
        background-color: #C5E2F4;
      }
    }
  }
</style>
