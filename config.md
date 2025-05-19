# Config file guide 

All the possible config options and correct practices for config are outlined in this file. 

## Overall structure 

```json
{
    "uid": {
        "type": "bubble-grid",
        "length": 10,
        "radius": 5,
        "x": {
            "0": 72,
            "1": 87,
            "2": 103,
            "3": 118,
            "4": 133.5,
            "5": 149,
            "6": 164,
            "7": 179.5,
            "8": 195,
            "9": 210,
            "10": 226
        },
        "y": {
            "0": 718,
            "1": 703,
            "2": 689,
            "3": 674,
            "4": 660,
            "5": 645,
            "6": 630.5,
            "7": 616,
            "8": 602,
            "9": 587
        },
        "text": {
            "y": 730,
            "fontSize": 10,
            "xOffset": -2
        }
    },
    "name": {
        "type": "text",
        "x": 350,
        "y": 600
    }
}
```

The config file is a json object with the top level key indicating the field name. This should have the same name as the data object provided to the `generateOMR` function. 

For example, the data type for the above mentioned config would look something like this (note the fields of the config object match the keys of the type):

```ts
type StudentData = {
    uid: string;
    name: string;
};
```

For each key of the config file, there are predefined subkeys outlined below. 

## Config type: 

One mandatory subkey is `type` which can either be `bubble-grid` or `text`. 

### `bubble-grid` type

This is for Roll numbers, UID etc which have a continuous numeric input (For example: numeric roll number like 12345 etc). The options / subkeys for `bubble-grid` type are: 

- `length` - Specifies the length of the Roll Number / UID
- `radius` - Specifies the radius of the bubble (Default: 5)
- `x` - Stores a sub object containng coordinates of the row of the Roll no / UID (Matches the length of the Roll no / UID). 
- `y` - Stores a sub object containing coordinates of the coloumn (Stores all digits from 0-9 in normal roll no)
- `text` - Can be added to print the text of the roll no / UID above the bubbles (Normal OMR Sheets have provisions for the actual text of the bubble to be written above)

The text subfield can have the following options: 

`y` - Specifies the y coordinate at which the text is rendered at.
`fontSize` - Specifies font size of the text. (Default: 10)
`xOffset` - Specifies the deviation of the text from the top row of the bubbles. 
 
### `text` type
`x` - Specifies the x coordinate of the text.
`y` - Specifies the y coordinate of the text.
