---
title: "How To"
component: "DatePicker"
description: "Miscellaneous aspects of customizing the date picker"
---

# JSON Data binding with DatePicker

In most of the real cases, the model data will be available with JSON format only.
 Here we have showcased DatePicker component by setting JSON string to value property.
In this JSON, we have used ISO formatted date string which is frequently used date format to get proper date and time value without any misreading.
Also our DatePicker component supports the ISO formatted date value, so parsed JSON value can be directly set to DatePicker model.

{% tab template="datepicker/json-bind", isDefaultActive = "true",  sourceFiles="app/**/*.ts,styles.css" %}

```typescript
import { Component } from '@angular/core';

export interface User {
    selectedDate: Date;
}
export interface JSONUser {
    selectedDate: string;
}
@Component({
    selector: 'app-root',
    template: `
    <!-- To Render DatePicker -->
    <ejs-datepicker id="datepicker" width='245px' [(value)]='user.selectedDate' (change)='onChange($event)'></ejs-datepicker>
    <div class="valuestring">
    <b>User model</b>:  <br/>{{user | json }}
    <br/><br/>
    <b>JSON Data</b>: <br/>{{ model_result }}
    <br/><br/>
    </div>`
})
export class AppComponent {
    public user: User;
    public JSONData: JSONUser = JSON.parse('{ "selectedDate": "2018-12-18T08:56:00+00:00"}');
    public model_result: string = JSON.stringify(this.JSONData);

    public ngOnInit() {
        this.user = this.JSONData;
    }
    onChange(args) {
        this.JSONData.selectedDate = args.value;
        this.model_result = JSON.stringify(this.JSONData);
    }
}

```

{% endtab %}
