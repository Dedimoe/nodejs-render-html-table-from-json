# nodejs-render-html-table-from-json
nodejs-render-html-table-from-json

```
let json=[
  { 
    'Province/State': 'West Virginia',
    'Country/Region': 'US',
    'Last Update': '2020-03-19T02:33:09',
    Confirmed: '2',
    Deaths: '0',
    Recovered: '0',
    Latitude: '38.4912',
    Longitude: '-80.9545' 
  },
  { 'Province/State': 'US',
    'Country/Region': 'US',
    'Last Update': '2020-03-19T19:13:18',
    Confirmed: '1',
    Deaths: '0',
    Recovered: '108',
    Latitude: '37.0902',
    Longitude: '-95.7129' 
  } ];
let tableHead=""
for(let column in json[0]){
  tableHead+=`<th>${column}</th>`
}
tableHead+="</tr>"
document.querySelector('#table_head').innerHTML=tableHead;

let tableBody=""
json.forEach(element => {
    tableBody+="<tr>"
    for(let prop in element){
      tableBody+=`<td>${element[prop]}</td>`
    }
    tableBody+="</tr>"
});


document.querySelector('#table_body').innerHTML=tableBody;
table {
  border: 1px solid;
}
```
```
table tr td{
  border-bottom: 1px solid;
}
table tr:last-child td{
  border-bottom: none;
}
```
```
<table>
  <thead id="table_head"></thead>
  <tbody id="table_body"></tbody>
</table>
```
