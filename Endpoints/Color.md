# Colors API
![Logo](/Images/color.jpg)

Colors are a important part of toxiq as it allows users to express themselves

#### GET
        api.toxiq.xyz/api/Color/DebugColorList
### Result

calling the endpoint will return an array of allowed colors  
- its important to only give users the option to select allowed colors  
- **do not call this endpoint more then once an app lifecycle** as this list wont change

```
[
  { "Hex": "#8a8a8a" }, //emo gray
  { "Hex": "#5a189a" }, //royal purple
  { "Hex": "#800e13" }, //bloody red
  { "Hex": "#375191" }, //4 blue
  { "Hex": "#ff4bb4" }, //barbie pink
  { "Hex": "#588157" } //forest green
]

```