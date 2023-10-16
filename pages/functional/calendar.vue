<template>
  <div class="group-box">
    <div class="wrapper">
      <header>
        <p class="current-date">{{ `${currMonth} ${currYear}` }}</p>
        <div class="icons">
          <span>
            <i class="pi pi-angle-left"></i>
          </span>
          <span>
            <i class="pi pi-angle-right"></i>
          </span>
        </div>
      </header>
      <div class="calendar">
        <ul class="weeks">
          <li>Пн</li>
          <li>Вт</li>
          <li>Ср</li>
          <li>Чт</li>
          <li>Пт</li>
          <li>Сб</li>
          <li>Вс</li>
        </ul>
        <ul class="days">
          <li class="inactive">28</li>
          <li class="inactive">29</li>
          <li class="inactive">30</li>
          <li class="inactive">31</li>
          <li>1</li>
          <li class="active">2</li>
          <li>3</li>
          <li>4</li>
          <li>5</li>
          <li>6</li>
          <li>7</li>
          <li>8</li>
          <li>9</li>
          <li>10</li>
          <li>11</li>
          <li>12</li>
          <li>13</li>
          <li>14</li>
          <li>15</li>
          <li>16</li>
          <li>17</li>
          <li>18</li>
          <li>19</li>
          <li>20</li>
          <li>21</li>
          <li>22</li>
          <li>23</li>
          <li>24</li>
          <li>25</li>
          <li>26</li>
          <li>27</li>
          <li>28</li>
          <li>29</li>
          <li>30</li>
          <li class="inactive">1</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">



</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body{
  display: flex;
  align-items: center;
  justify-content: center;
}
.group-box{
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #9b59b6 !important;
  min-height: 100vh;
}
.wrapper{
  background: #fff;
  border-radius: 10px;
}
.wrapper header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 30px 20px;
}
header .current-date {
  color: #2c3e50;
  font-size: 24px;
  font-weight: 500;
}
header .icons span i{
  width: 40px;
  height: 40px;
  margin: 0 1px;
  text-align: center;
  line-height: 38px;
  font-size: 20px;
  border-radius: 50%;
  cursor: pointer;
  color: #878787;
}
header .icons span i:hover {
  background: #f2f2f2;
}
header .icons span i:last-child{
  margin-right: 10px;
}
.calendar ul {
  display: flex;
  list-style: none;
  flex-wrap: wrap;
  text-align: center;
  padding: 0 10px;
  padding-bottom: 20px;
}
.calendar .weeks {
  padding-bottom: 5px;
}
.calendar .weeks li {
  font-weight: 600;
}
.calendar .days {
  margin-bottom: 10px;
}
.calendar .days li {
  margin-top: 20px;
}
.calendar ul li {
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1;
  width: calc(100% / 7);
  transition: .2s;
  cursor: pointer;
}
.calendar ul li::before {
  position: absolute;
  content: '';
  width: 40px;
  height: 40px;
  z-index: -1;
  border-radius: 50%;
}
.calendar ul li:hover::before{
  background: #878787;
}
.calendar ul li.inactive{
  color: #c9c9c9;
}
.calendar ul li.active {
  display: flex;
  align-items: center;
  justify-content: center ;
  color: #fff;
}
.calendar ul li.active::before {
  position: absolute;
  content: '';
  width: 40px;
  height: 40px;
  background: #9b59b6;
}
</style>