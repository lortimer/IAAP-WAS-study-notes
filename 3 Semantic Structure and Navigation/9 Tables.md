# Tables

## Semantic Markup for Tabular Data

### Tabular data SHOULD be represented in a `<table>`

Screen readers have special controls for navigating properly-marked-up tables, like you would navigate an excel
spreadsheet.

#### Don't create fake tables

Tables don't always display properly on mobile devices, so some developers use `div`s and CSS to recreate the look of
tables without the proper markdown. Screen readers can't read these tables properly, and users can't navigate the tables
in the usual way. Users can only read the tables sequentially.

If your table won't work on mobile, consider alternative formats.

## Table caption/name

### Data tables SHOULD have a programmatically-associated caption or name

The caption is read when a user navigates to a table.

When users view a list of tables in the document, a screen reader will read the captions and some meta information about
the table like number of columns and rows. Without captions, a series of similar tables are indistinguishable in a
screen reader.

### The name/caption of a data table SHOULD describe the identity or purpose of the table accurately, meaningfully, and succinctly

### The name/caption of each data table SHOULD be unique within the context of other tables on the same page

## Table Headers

### Table headers MUST be designated with `<th>`

### Data table header text MUST accurately describe the category of the corresponding data cells

Don't name it generically like "Column 3" or include extraneous information like links, buttons, or extra description.

## Simple Header Associations

### Table data cells MUST be associated with their corresponding header cells

If the header cells are in the first row, there is an implicit `scope="col"` in them. It's best to explicitly specify
the `scope` for each header as `col`, `row`, `colgroup`, or `rowgroup`.

`col` and `row` are preferred for simplicity.

Good example:

<table class="data">
<caption><strong>Greensprings Running Club Personal Bests</strong></caption>
<thead>
<tr>
<th scope="col">Name</th>
<th scope="col">1 mile</th>
<th scope="col">5 km</th>
<th scope="col">10 km</th>
</tr>
</thead>

<tbody>
<tr>
<th scope="row">Mary</th>
<td>8:32</td>
<td>28:04</td>
<td>1:01:16</td>
</tr>

<tr>
<th scope="row">Betsy</th>
<td>7:43</td>
<td>26:47</td>
<td>55:38</td>
</tr>

<tr>
<th scope="row">Matt</th>
<td>7:55</td>
<td>27:29</td>
<td>57:04</td>
</tr>

<tr>
<th scope="row">Todd</th>
<td>7:01</td>
<td>24:21</td>
<td>50:35</td>
</tr>
</tbody>

</table>

```html

<table>
    <caption><strong>Greensprings Running Club Personal Bests</strong></caption>
    <thead>
    <tr>
        <th scope="col">Name</th>
        <th scope="col">1 mile</th>
        <th scope="col">5 km</th>
        <th scope="col">10 km</th>
    </tr>
    </thead>

    <tbody>
    <tr>
        <th scope="row">Mary</th>
        <td>8:32</td>
        <td>28:04</td>
        <td>1:01:16</td>
    </tr>

    <tr>
        <th scope="row">Betsy</th>
        <td>7:43</td>
        <td>26:47</td>
        <td>55:38</td>
    </tr>

    <tr>
        <th scope="row">Matt</th>
        <td>7:55</td>
        <td>27:29</td>
        <td>57:04</td>
    </tr>

    <tr>
        <th scope="row">Todd</th>
        <td>7:01</td>
        <td>24:21</td>
        <td>50:35</td>
    </tr>
    </tbody>

</table>
```

## Grouped Header Associations

### Table data group headers MUST be associated with their corresponding data cell groups

When you merge header cells, you have to use scope to specify that it corresponds to multiple rows.

Header groups are still confusing. If possible, don't use them.

Here is a well-marked-up table that doesn't need its header groups because sex is non-binary and gender is a construct:

<table class="data complex">
  <caption>
    Table with colgroup
  </caption>
  <thead>
    <tr>
      <td rowspan="2">&nbsp;</td>
      <th colspan="3" scope="colgroup">Females</th>
      <th colspan="3" scope="colgroup">Males</th>
    </tr>
    <tr>
      <th scope="col">Mary</th>
      <th scope="col">Betsy</th>
      <th scope="col">Joanne</th>
      <th scope="col">Matt</th>
      <th scope="col">Todd</th>
      <th scope="col">Jake</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1 mile</th>
      <td>8:32</td>
      <td>7:43</td>
      <td>9:51</td>
      <td>7:55</td>
      <td>7:01</td>
      <td>7:51</td>
    </tr>
    <tr>
      <th scope="row">5 km</th>
      <td>28:04</td>
      <td>26:47</td>
      <td>38:15</td>
      <td>27:27</td>
      <td>24:21</td>
      <td>24:31</td>
    </tr>
    <tr>
      <th scope="row">10 km</th>
      <td>1:01:16</td>
      <td>55:38</td>
      <td>1:56:01</td>
      <td>57:04</td>
      <td>50:35</td>
      <td>50:45</td>
    </tr>
  </tbody>
</table>

```html

<table class="data complex">
    <caption>
        Table with colgroup
    </caption>
    <thead>
    <tr>
        <td rowspan="2">&nbsp;</td>
        <th colspan="3" scope="colgroup">Females</th>
        <th colspan="3" scope="colgroup">Males</th>
    </tr>
    <tr>
        <th scope="col">Mary</th>
        <th scope="col">Betsy</th>
        <th scope="col">Joanne</th>
        <th scope="col">Matt</th>
        <th scope="col">Todd</th>
        <th scope="col">Jake</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th scope="row">1 mile</th>
        <td>8:32</td>
        <td>7:43</td>
        <td>9:51</td>
        <td>7:55</td>
        <td>7:01</td>
        <td>7:51</td>
    </tr>
    <tr>
        <th scope="row">5 km</th>
        <td>28:04</td>
        <td>26:47</td>
        <td>38:15</td>
        <td>27:27</td>
        <td>24:21</td>
        <td>24:31</td>
    </tr>
    <tr>
        <th scope="row">10 km</th>
        <td>1:01:16</td>
        <td>55:38</td>
        <td>1:56:01</td>
        <td>57:04</td>
        <td>50:35</td>
        <td>50:45</td>
    </tr>
    </tbody>
</table>
```

#### Special note about `colgroup` and `rowgroup`

Screen reader support for `rowgroup` has historically been worse than for `colgroup`. If you're going to group headers,
do it in columns.

## Complex Header Associations

### Header/data associations that cannot be designated with <th> and scope MUST be designated with headers plus id

Very complex tables where cells are merged or there are more that 2 levels of headers require more complex markdown -
Each data cell must be explicitly associated with each corresponding header cell using `headers` and `id`

#### Warning

Don't do this! This is only for the most dire of emergencies where you cannot change the structure of the data you are
presenting.

Some screen readers don't even support this!

#### "Good" Example

<table class="complexexample">
  <caption>New Employee Orientation Schedule</caption>
  <tbody>
    <tr>
      <th rowspan="2" id="date">Date</th>
      <th colspan="2" id="schedule">Schedule</th>
      <th rowspan="2" id="location">Location</th>
      <th colspan="2" rowspan="2" id="topics1">Topics</th>
    </tr>
    <tr>
      <th id="start">Start</th>
      <th id="end">End</th>
    </tr>
    <tr>
      <th id="monday" rowspan="5">Monday, June 1</th>
      <td headers="schedule start monday">9:00 a.m.</td>
      <td headers="schedule end monday">10:30 a.m.</td>
      <td headers="location monday">RH 001</td>
      <td headers="topics1 monday">
        Introduction to Company: Vision and Mission</td>
    </tr>
    <tr>
      <td headers="schedule start monday">10:30 a.m.</td>
      <td headers="schedule end monday">12:00 p.m.</td>
      <td headers="location monday">RH 001</td>
      <td headers="topics1 monday">HR Policies Review</td>
    </tr>
    <tr>
      <td headers="schedule monday" colspan="5">
        <strong><em>
          Lunch from 12:00 p.m. to 1:00 p.m.
        </em></strong>
      </td>
    </tr>
    <tr>
      <td headers="schedule start monday">1:00 p.m.</td> 
      <td headers="schedule end monday">2:30 p.m.</td>
      <td headers="location monday">RH 001</td>
      <td headers="topics1 monday">Overview of Benefits</td>
    </tr>
    <tr>
      <td headers="schedule start monday">3:00 p.m.</td>
      <td headers="schedule end monday">4:30 p.m.</td>
      <td headers="location monday">RH 005</td>
      <td headers="topics1 monday">
        Health and Safety Procedures
      </td>
    </tr>
  </tbody>
</table>

```html

<table class="complexexample">
    <caption>New Employee Orientation Schedule</caption>
    <tbody>
    <tr>
        <th rowspan="2" id="date">Date</th>
        <th colspan="2" id="schedule">Schedule</th>
        <th rowspan="2" id="location">Location</th>
        <th colspan="2" rowspan="2" id="topics1">Topics</th>
    </tr>
    <tr>
        <th id="start">Start</th>
        <th id="end">End</th>
    </tr>
    <tr>
        <th id="monday" rowspan="5">Monday, June 1</th>
        <td headers="schedule start monday">9:00 a.m.</td>
        <td headers="schedule end monday">10:30 a.m.</td>
        <td headers="location monday">RH 001</td>
        <td headers="topics1 monday">
            Introduction to Company: Vision and Mission
        </td>
    </tr>
    <tr>
        <td headers="schedule start monday">10:30 a.m.</td>
        <td headers="schedule end monday">12:00 p.m.</td>
        <td headers="location monday">RH 001</td>
        <td headers="topics1 monday">HR Policies Review</td>
    </tr>
    <tr>
        <td headers="schedule monday" colspan="5">
            <strong><em>
                Lunch from 12:00 p.m. to 1:00 p.m.
            </em></strong>
        </td>
    </tr>
    <tr>
        <td headers="schedule start monday">1:00 p.m.</td>
        <td headers="schedule end monday">2:30 p.m.</td>
        <td headers="location monday">RH 001</td>
        <td headers="topics1 monday">Overview of Benefits</td>
    </tr>
    <tr>
        <td headers="schedule start monday">3:00 p.m.</td>
        <td headers="schedule end monday">4:30 p.m.</td>
        <td headers="location monday">RH 005</td>
        <td headers="topics1 monday">
            Health and Safety Procedures
        </td>
    </tr>
    </tbody>
</table>
```

## Nested or Split tables

### Data table headers and data associations MUST NOT be referenced across nested, merged, or separate tables

Nested tables are tables in tables. This fully breaks accessibility features.

Don't reference data between 2 separate tables.

## Table Summary

### A summary MAY be provided for data tables

A table summary is like having to explain a design or provide instructions - not ideal and a smell that there's room for
improvement. I can be helpful, though, especially if something is unusual about the data.

Brevity and Concision are key.

#### The methods:

1. Put a summary paragraph before or after and use `aria-describedby`
2. Put the summart in the table's caption as long as it is very brief
3. Put the table in a `figure` and put the title and summary in a `figcaption`
4. ~~Put the summary in the `summary` attribute of the table~~
    1. **REMOVED IN HTML5**

Good Example: Put a summary paragraph before or after and use `aria-describedby`

```html
<p id="table-description">This table lists the members of the
    Greensprings Running Club and their personal best times in various race distances.
    The first column lists the runners and the first row lists the race distances.</p>

<table aria-describedby="table-description">
    ...
</table>
```

Good example: Put the table in a `figure` and put the title and summary in a `figcaption`

```html
<figure>
   <figcaption id="table_figcaption">
      Greensprings Running Club Personal Bests<br>
      (The first column lists the runners and the
      first row lists the race distances)
   </figcaption>
   <table aria-labelledby="table_figcaption">
   ...
   </table>
<figure>
```

### A data table summary, if provided, SHOULD make the table more understandable to screen reader users.

Don't use it for keyword stuffing or use an overly long summary.

## Layout Tables

### Tables SHOULD NOT be used for the purpose of purely visual (non-data) layout

If you do this, you should add `role="presentation"` so screen readers read the contents of the table as text instead of data cells.

### Layout tables MUST NOT contain data table markup

Specifically, they must not include:
- The <caption> element
- The <summary> attribute
- The <th> element
- The scope attribute
- The headers attribute

