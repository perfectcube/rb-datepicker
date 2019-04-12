# TODO:

### Description

These attributes/callbacks need to be implemented:

#### Options

- [x] **minDate** & **maxDate**: work as expected

```jsx
minDate={moment().startOf('hour').add(32, 'hour')}
maxDate={moment().startOf('hour').add(32, 'hour')}
```

- [ ] **singleDatePicker**: currently non-functional, should automatically switch between <LinkedCalendar> and <Calendar>

```jsx
singleDatePicker={true|false}
```

- [ ] **startDate** & **endDate**: these can be set. However if you do the it breaks the selection of other dates

```jsx
startDate={moment().startOf('hour')}
endDate={moment().startOf('hour').add(32, 'hour')}
```

- [ ] **minYear** & **minYear**: don't stop selection or display of any given year

```jsx
minYear={2018}
maxYear={parseInt(moment().format('YYYY'),1)}
```

- [ ] **ranges**: has no effect; should build out a predefined dates selector and hide calendars unless `alwaysShowCalendars={true}`

```jsx
ranges={{
	'Today': [moment(), moment()],
	'Yesterday': [moment().subtract(1, 'days'), moment().subtract(1, 'days')],
	'Last 7 Days': [moment().subtract(6, 'days'), moment()],
	'Last 30 Days': [moment().subtract(29, 'days'), moment()],
	'This Month': [moment().startOf('month'), moment().endOf('month')],
	'Last Month': [moment().subtract(1, 'month').startOf('month'), moment().subtract(1, 'month').endOf('month')]
}}
```

- [ ] **alwaysShowCalendars**: no effect; should show calendars when ranges are provided 

```jsx
alwaysShowCalendars={false}
```

- [ ] **maxSpan**.{**days**|**months**|**years**}: has no effect; should preselect first_day + days range if second selection is outside of maxSpan.{days|months|years}

```jsx
maxSpan={{"days": 7}}
```

- [ ] **locale**: setting locale to any object value, with or without the below keys, will hide weekday names

```jsx
locale={{
	"format": "MM/DD/YYYY",
	"separator": " - ",
	"applyLabel": "Apply",
	"cancelLabel": "Cancel",
	"fromLabel": "From",
	"toLabel": "To",
	"customRangeLabel": "Custom",
	"weekLabel": "W",
	"daysOfWeek": [
		"Su",
		"Mo",
		"Tu",
		"We",
		"Th",
		"Fr",
		"Sa"
	],
	"monthNames": [
		"January",
		"February",
		"March",
		"April",
		"May",
		"June",
		"July",
		"August",
		"September",
		"October",
		"November",
		"December"
	],
	"firstDay": 1
}}
```

- [ ] **timePicker\***: has no effect, should produce time picker below calendars     

```jsx
timePicker={true|false}
timePickerSeconds={true|false}
timePicker24Hour={true|false}
```

- [ ]  **autoApply**: has no effect     

```jsx
autoApply={true}
```

- [ ] **opens & drops**: are not currently available as <LinkedCalendar> and <Calendar> don''t come attached to an input field

```jsx
opens={"left"|"center"|"right"}
drops={"up"|"down"}
```

- [ ] **\*buttonClasses**: have no effect; should add custom classes on "cancel" and "apply" buttons

```jsx
buttonClasses="common-picker-class"
applyButtonClasses="apply-button-class"
cancelButtonClasses="cancel-button-class"
```

- [ ] **autoUpdateInput**: (true/false) Indicates whether the date range picker should automatically update the value of the <input> element it's attached to at initialization and when the selected dates change.

###Methods/EventCallbacks

- [ ] **isInvalidDate**: (function) A function that is passed each date in the two calendars before they are displayed, and may return true or false to indicate whether that date should be available for selection or not.

- [ ] **isCustomDate**: (function) A function that is passed each date in the two calendars before they are displayed, and may return a string or array of CSS class names to apply to that date's calendar cell.

- [ ] **setStartDate**(*Date*|*String*): Sets the date range picker's currently selected start date to the provided date

- [ ] **setEndDate**(*Date*|*String*): Sets the date range picker's currently selected end date to the provided date

- [ ] **onShow**: Triggered when the picker is shown

- [ ] **onHide**: Triggered when the picker is hidden

- [ ] **onShowCalendar**: Triggered when the calendar(s) are shown

- [ ] **onHideCalendar**: Triggered when the calendar(s) are hidden

- [ ] **onApply**: Triggered when the apply button is clicked, or when a predefined range is clicked

- [ ] **onCancel**: Triggered when the cancel button is clicked