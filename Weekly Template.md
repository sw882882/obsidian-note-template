<%tp.file.rename("Weekly Notes") /* I have to do this for some reason because it wont let me name normally for whatever reason, this fixed the bug*/%>
## Week Overview
### ☑ Todo
<%*
folder = tp.file.folder(relative=true)
const weekday = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]
// doing things in a very roundabout way because templater is being uncooperative
const year = folder.split('/').slice(1, 2).join('/');
const week = parseInt((folder.split('/').slice(2, 3).join('/')).slice(-1));
for (let i = 0; i < 7; i++) {  
	day = weekday[i]
	dayNo = tp.date.weekday("DD", i, year.concat(String(week).padStart(2, "0")), "YYYYww")
	tR += `#### ${day}\n`;
	tR += `![[${folder}/${dayNo}-${day}#✓ Things I plan to accomplish today]]\n\n`;
}
%>

### 📈 Weekly Stats
```dataviewjs

```

```dataviewjs
const folder = "<%tp.file.folder(relative=true)%>"
const weekday = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]
// doing things in a very roundabout way because templater is being uncooperative
const year = folder.split('/').slice(1, 2).join('/');
const week = parseInt((folder.split('/').slice(2, 3).join('/')).slice(-1));



var one = undefined;
dayNo = "<%tp.date.weekday("DD", 0, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
one = dv.page(folder.concat("/", dayNo.concat("-", weekday[0])));
if (one==undefined) { one = 0; }

var two = undefined;
dayNo = "<%tp.date.weekday("DD", 1, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
two = dv.page(folder.concat("/", dayNo.concat("-", weekday[1])));
if (two==undefined) { two = 0; }

var thr = undefined;
dayNo = "<%tp.date.weekday("DD", 2, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
thr = dv.page(folder.concat("/", dayNo.concat("-", weekday[2])));
if (thr==undefined) { thr = 0; }

var fou = undefined;
dayNo = "<%tp.date.weekday("DD", 3, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
fou = dv.page(folder.concat("/", dayNo.concat("-", weekday[3])));
if (fou==undefined) { fou = 0; }

var fiv = undefined;
dayNo = "<%tp.date.weekday("DD", 4, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
fiv = dv.page(folder.concat("/", dayNo.concat("-", weekday[4])));
if (fiv==undefined) { fiv = 0; }

var six = undefined;
dayNo = "<%tp.date.weekday("DD", 5, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
six = dv.page(folder.concat("/", dayNo.concat("-", weekday[5])));
if (six==undefined) { six = 0; }

var sev = undefined;
dayNo = "<%tp.date.weekday("DD", 6, year.concat(String(week).padStart(2, "0")), "YYYYww")%>"
sev = dv.page(folder.concat("/", dayNo.concat("-", weekday[6])));
if (sev==undefined) { sev = 0; }

const chartData = {
    type: 'line',
    data: {
        labels: weekday,
        datasets: [{
            label: "Happyness",
            data: [one.happyness, two.happyness, thr.happyness, fou.happyness, fiv.happyness, six.happyness, sev.happyness],
            backgroundColor: 'rgba(255, 99, 132, 0.2)',
            borderColor: 'rgba(255, 99, 132, 1)',
            borderWidth: 1,
			fill: false,
			tension: 0.2
        },	{
			label: "Stress",
			data: [one["stress"], two["stress"], thr["stress"], fou["stress"], fiv["stress"], six["stress"], sev["stress"]],
			backgroundColor: 'rgba(85, 174, 229, 0.2)',
            borderColor: 'rgba(85, 174, 229, 1)',
            borderWidth: 1,
			fill: false,
			tension: 0.2
		}, {
			label: "Hours Worked",
			data: [one["hours-worked"], two["hours-worked"], thr["hours-worked"], fou["hours-worked"], fiv["hours-worked"], six["hours-worked"], sev["hours-worked"]],
			backgroundColor: 'rgba(255, 211, 101, 0.2)',
            borderColor: 'rgba(255, 211, 101, 1)',
            borderWidth: 1,
			fill: false,
			tension: 0.2
		}, {
			label: "Hours Slept",
			data: [one["hours-slept"], two["hours-slept"], thr["hours-slept"], fou["hours-slept"], fiv["hours-slept"], six["hours-slept"], sev["hours-slept"]],
			backgroundColor: 'rgba(92, 197, 193, 0.2)',
            borderColor: 'rgba(92, 197, 193, 1)',
            borderWidth: 1,
			fill: false,
			tension: 0.2
		}, {
			label: "Productivity",
			data: [one.productivity, two.productivity, thr.productivity, fou.productivity, fiv.productivity, six.productivity, sev.productivity],
			backgroundColor: 'rgba(153, 50, 204, 0.2)',
            borderColor: 'rgba(153, 50, 204, 1)',
            borderWidth: 1,
			fill: false,
			tension: 0.2
		}],
    },
	options: {
		scales: {
		    y: {
		        min: 0,
		        max: 10,
			}
	    }
	}
}

window.renderChart(chartData, this.container);
```
<%
//TODO: compare with past week

%>

### 📅 Weekly Questions

##### 👍 One thing I should do next week

- 

##### 👎 One difficult thing this week is...

- 

##### ☑ One thing I've accomplished this week is...

- 
