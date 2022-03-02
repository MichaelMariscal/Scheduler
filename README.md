# Scheduler

# Overview

{This is simple scheduling application that I designed to be used in a setting where users need something to keep track of appointments. A user would talk to the client to set up a time to meet and the owner would use this as a guide to schedule multiple people without double booking themselves. A user can add and delete certain appointments depending on their availability.}

{The reason I wrote this was to start a program that I can expand on and further deliver a functioning product to customers who uses a weekly scheduler. Such as hair stylists, nail techs, etc. My wife is a nail technician and having anywhere from 20-35 clients at a time, scheduling can be difficult since she has to plan out in advance and I wanted to create something that can ease that proccess. }

[Software Demo Video](http://youtube.link.goes.here)

# Development Environment

{For this program, I used Codepen.io since it is a web developing website. I like the feautre of auto-updating since I can see my work up to date right on the next screen.}

{For this program, I used HTML, CSS, and Javascript.}

# Useful Websites

{Make a list of websites that you found helpful in this project}
* [CodePen.io](https://codepen.io/)


# Future Work


* Item 1 - Something that I would like to introduce is a user interface that the customer can logon to make their own appointment. They can see a certain block of availability and they can select a certain time to meet.
* Item 2 - With a user interface, I would like to have a master control where the owner can go in and make any changes to appointment, for example, they can delete someones appointment if they were not able to make it or just simply change the time to meet.


# Code Source 
Javascript
'''
<div class="timetable">
  <table class="button-options">
    <tr>
      <th></th>
      <th id="addBooking">Add Booking</th>
      <th id="deleteBooking">Delete Selected</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th id="printSchedule"Print</th>
    </tr>
  </table>
  <div class="layoutdesign">
    <div class="row">
      <div></div>
      <div>10:00am</div>
      <div>11:15am</div>
      <div>12:30pm</div>
      <div>1:45pm</div>
      <div>2:00pm</div>
      <div>3:15pm</div>
      <div>4:30pm</div>
      <div>5:45pm</div>
      <div>6:00pm</div>
      <div>7:15pm</div>
   
    </div>
    <div class="row">
      <div>Monday</div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
    <div class="row">
      <div>Tuesday</div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>

    <div class="row">
      <div>Wednesday</div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
    <div class="row">
      <div>Thursday</div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
    <div class="row">
      <div>Friday</div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>    
   <span class="Booking" style="top:10vh;left:calc(10vw + 225px); width:180px" data-start="02:00">Susy-70mins</span>
  </div>
  <form>
    <input id="timetableBooking" type="text" placeholder="Enter Name" />
    <input id="timetableDuration" type="text" placeholder="Enter Duration (mins)" />
    <input id="timetableStart" type="text" placeholder="Time (HH:MM)" />
    <select id="timetableScreen">
      <option>Monday</option>
      <option>Tuesday</option>
      <option>Wednesday</option>
      <option>Thursday</option>
      <option>Friday</option>
    </select>
  </form>

</div>


'''
CSS
'''
.timetable {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}

.timetable .button-options {
  position: fixed;
  width: 100%;
  background: pink;
  height: 10%;
  top: 0;
  left: 0;
}

.timetable .button-options th {
  box-shadow: inset 0 0 2px rgba(0, 0, 0, 0.2);
  width: 10%;
}

.timetable .layoutdesign {
  margin-top: 12vh;
  background: wihte;
  font-size: 0;
  overflow-x: auto;
  overflow-y: hidden;
  white-space: nowrap;
  position: relative;
}

.timetable * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.timetable .layoutdesign .row div {
  width: 135px;
  display: inline-block;
  font-size: initial;
  height: 8vh;
  border-left: 8px dashed rgba(0, 0, 0, 0.1);
  text-align: left;
  vertical-align: top;
}

.timetable .layoutdesign .row div:first-child {
  width: 10%;
  border: none;
}

.timetable .layoutdesign .row:not(:first-child) div {
  height: 15vh;
  border-top: 4px dashed rgba(0, 0, 0, 0.1);
  background: rgba(50, 0, 0, 0.1);
  text-align: center;
}

.timetable .layoutdesign .row div:first-child {
  position: fixed;
  background: pink;
  z-index: 30;
}

.timetable .layoutdesign .row div:nth-child(2) {
  margin-left: 10vw
}

.timetable form {
  margin-top: 20px;
}

.timetable .booking {
  position: absolute;
  background: gold;
  box-shadow: inset 0 0 0 2px #222;
  height: 5vh;
  border-radius:5px;
  line-height: 5vh;
  color: #222;
  background:gold;
  font-size: 15px;overflow:hidden;
  text-align: center;
}

.timetable .booking:before {
  content: attr(data-start);
  position: absolute;
  top: 2px;
  color: #222;height:10px;
  font-size: 10px;
  line-height:10px;
  left:2px;
}

.timetable .booking.activeBooking {
  background: red;
}

.selectable .active{
    background:red !important;
}

.bookingSelector{
  width:100%;
  height:98px;margin-top:20px;
  overflow:hidden;background:rgba(0,0,0,0.2);
}
.bookingSelector .slot{display:inline-block;margin:5px; border:5px solid black; padding:10px; width:15%;text-align:center;background:#eee;color:#222;
}
.bookingSelector .time.slot{background:#222;color:#eee}
.bookingSelector .slot:active{background:gold;color:#222;}
.bookingSelector:hover{height:150px;}

.bookingSelector .time.slot.active{background:gold;color:#222;}

'''
Javascript
'''
.timetable {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}

.timetable .button-options {
  position: fixed;
  width: 100%;
  background: gray;
  height: 10%;
  top: 0;
  left: 0;
}

.timetable .button-options th {
  box-shadow: inset 0 0 2px rgba(0, 0, 0, 0.2);
  width: 10%;
}

.timetable .layoutdesign {
  margin-top: 12vh;
  background: white;
  font-size: 0;
  overflow-x: auto;
  overflow-y: hidden;
  white-space: nowrap;
  position: relative;
}

.timetable * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}

.timetable .layoutdesign .row div {
  width: 100px;
  display: inline-block;
  font-size: initial;
  height: 5vh;
  border-left: 2px dashed rgba(0, 0, 0, 0.1);
  text-align: left;
  vertical-align: top;
}

.timetable .layoutdesign .row div:first-child {
  width: 10%;
  border: none;
}

.timetable .layoutdesign .row:not(:first-child) div {
  height: 10vh;
  border-top: 2px dashed rgba(0, 0, 0, 0.1);
  background: rgba(0, 0, 0, 0.1);
  text-align: center;
}

.timetable .layoutdesign .row div:first-child {
  position: fixed;
  background: gray;
  z-index: 30;
}

.timetable .layoutdesign .row div:nth-child(2) {
  margin-left: 10vw
}

.timetable form {
  margin-top: 20px;
}

.timetable .booking {
  position: absolute;
  background: gold;
  box-shadow: inset 0 0 0 2px #222;
  height: 5vh;
  border-radius:5px;
  line-height: 5vh;
  color: #222;
  background:gold;
  font-size: 15px;overflow:hidden;
  text-align: center;
}

.timetable .booking:before {
  content: attr(data-start);
  position: absolute;
  top: 2px;
  color: #222;height:10px;
  font-size: 10px;
  line-height:10px;
  left:2px;
}

.timetable .booking.activeBooking {
  background: red;
}

.selectable .active{
    background:red !important;
}

.filmSelector{
  width:100%;
  height:98px;margin-top:20px;
  overflow:hidden;background:rgba(0,0,0,0.2);
}
.filmSelector .slot{display:inline-block;margin:5px; border:5px solid black; padding:10px; width:15%;text-align:center;background:#eee;color:#222;
}
.filmSelector .time.slot{background:#222;color:#eee}
.filmSelector .slot:active{background:gold;color:#222;}
.filmSelector:hover{height:150px;}

.filmSelector .time.slot.active{background:gold;color:#222;}


'''

