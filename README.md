#Bootstrap v3 datetimepicker widget

Examples and documentation can be found [here](http://eonasdan.github.io/bootstrap-datetimepicker/).

Options (updated)
=================

```js
$.fn.datetimepicker.defaults = {
    pickDate: true,             // disables the date picker
    pickTime: true,             // disables de time picker
    startDate:  -Infinity,      // set a minimum date
    endDate: Infinity,          // set a maximum date
    useStrict: false,           //use "strict" when validating dates
    collapse: true,             // Collapse the time picker
    icons: {
        time: 'glyphicon glyphicon-time',
        date: 'glyphicon glyphicon-calendar',
        up:   'glyphicon glyphicon-chevron-up',
        down: 'glyphicon glyphicon-chevron-down'
    }
};
```

Events
======
`change.dp`
Fires when the datepicker changes or updates the date

`show.dp`
Fires when the widget is shown

`hide.dp`
Fires when the widget is hiden

`errors.dp`
Fires when Moment cannot parse the date or when the timepicker 
cannot change because of a `disabledDates` setting. Returns a 
Moment date object. The specific error can be found be using 
`invalidAt()`. For more information see 
[Moment's docs](http://momentjs.com/docs/#/parsing/is-valid/).

Changelog
=========

#### 2.1.11
* Fix for #51, #60
* Fix for #52: Picker has its own `moment` object since moment 2.4.0 has removed global reference
* Fix for #57: New option for `useStrict`. When validating dates in `update` and `change`, the picker can use a stricter formatting validation
* Fix for #61: Picker should now properly take formatted date. Should also have correct start of the week for locales.
* Fix for #62: Default format will properly validate time picker only.

#### 2.1.5
* Custom icons, such as Font Awesome, are now supported. (#49)  See [Example#9](http://eonasdan.github.io/bootstrap-datetimepicker/#example9)
* If more then one `input-group-addon` is present use `datepickerbutton` to identify where the picker should popup from. (#48)
* New Event: `error.dp`. Fires when Moment cannot parse the date or when the timepicker cannot change because of a `disabledDates` setting. Returns a Moment date object. The specific error can be found be using `invalidAt()`. For more information see [Moment's docs](http://momentjs.com/docs/#/parsing/is-valid/)
* Fix for #42, plugin will now check for `A` or `a` in the format string to determine if the AM/PM selector should display.
* Fix for #45, fixed null/empty and invalid dates
* Fix for #46, fixed active date highlighting
* Fix for #47, `change.dp` event to also include the previous date.

#### 2.0.1
* New event `error.dp` fires when plugin cannot parse date or when increase/descreasing hours/minutes to a disabled date.  See [Example#7](http://eonasdan.github.io/bootstrap-datetimepicker/#example7)
* Minor fixes

#### 2.0.0
* `disabledDates` is now an option to set the disabled dates. It accepts date objects like `new Date("November 12, 2013 00:00:00")` and `12/25/2013' and `moment` date objects. See [Example#7](http://eonasdan.github.io/bootstrap-datetimepicker/#example7) for usage.
* Events are easier to use; see [Example#8](http://eonasdan.github.io/bootstrap-datetimepicker/#example8)
* Removed pickSeconds option
* Removed pick12HourFormat option
* Removed maskInput option