
Chronos parses Markdown in chronos code blocks into objects on a timeline

```chronos
@ [2025~2026] Year of the Snake
```
The first character of each line in your chronos block determines the item type:

- Events (-) Must be a single date
- Periods (@) Must be a range with start and end
- Points (`*`) Must be a single date
- Markers (=) Must be a single date
- Comments (#) Not displayed
- Flags (>) 
	- `> NOTODAY ` hide the vertical bar that marks todays's time
	- `> ORDERBY start` order the stack of overlapping items by start date

## A note on dates
```
- [2020] A year
- [2020-02] A month
- [2020-02-28] A day
- [2020-02-28T12] An hour
- [2020-02-28T12:30] A minute
- [2020-02-28T12:30:09] A second
```
Date ranges are separated by a tilde `~`, **NOT a hyphen**! Look out :)

### Events with descriptions
**Example**


```chronos
- [1991~2001] Time I believed in Santa | ended when my brother tried to videotape Santa with a hidden camera
```

## Modifiers
Modifiers `#color` and {Group} can be added to Events (-) and Periods (@) with the following optional syntax. 
To give items a specific color, you can include an available color after the date: `
```
#red | #orange #yellow #green #blue #purple #pink #cyan
```

```chronos
- [2001~2009] #red Bush
- [2009~2017] #blue Obama
- [2017~2021] #red Trump
- [2021~2025] #blue Biden

@ [2020-03-11~2023-05-11] #pink COVID19
```
**Events** and **Periods** can be grouped into "swimlanes" by specifying a `Group Name` in curly brackets `{}` after the `Date` (or `Color`, if present). Group names are case sensitive and may contain spaces.


```chronos
@ [1892-10-08~1941-08-31]{Marina Tsvetaeva} 1892-1941
- [1916] {Marina Tsvetaeva} "Подруга"
- [1928] {Marina Tsvetaeva}  "Поэма концов"
- [1941] {Marina Tsvetaeva} "Записки о поэзии"

@[1899-08-24~1986-06-14]{Jorge Luis Borges} 1899-1986
- [1944] {Jorge Luis Borges} "Ficciones"
- [1949] {Jorge Luis Borges} "El Aleph"
- [1962] {Jorge Luis Borges} "Labyrinths"
```

Adding a link to chronos
```chronos
- [2021~2022] No link
- [2023~2024] With link [[Lab To Dos]]
- [2022~2024] Link in description | [[SBT Analysis Meeting 2025]]
* [2022] Link in description | [[Testbeam Analysis]]
```
