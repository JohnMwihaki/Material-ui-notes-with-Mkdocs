# Material UI(MUI)

###  What is Material UI?

Material UI (MUI) is a React component library that helps developers build beautiful, consistent, and responsive user interfaces quickly using pre-built components.

**What is a Component Library?**

A component library is like a toolbox full of ready-made UI elements (called components) that you can use in your React application instead of building everything from scratch.

*Simple Analogy*

Imagine building a house:

Without tools = you make every brick yourself.

With tools (like MUI) = you have bricks, doors, windows, paint ready to use.

## What is Material Design

Definition:
Material Design is a design language created by Google. 
Material Design is a set of guidelines that define how elements should look, feel, and interact across all devices and platforms.
It gives rules and guidelines on:

- How things should look (e.g., rounded buttons, shadows)

- How they should behave (e.g., animations, spacing)

- How they should respond on different screen sizes (responsiveness)

MUI is built based on the material Design stardard

## Core Principles of Material Design

 **Elevation**

- Elevation is the idea of giving UI elements depth by using shadows.Buttons "float" above the surface.Cards have a shadow to stand out from the background

Every component has a elevation prop (e.g., <Paper elevation={3} />)

**Spacing (Consistent Padding & Margin)**

- Spacing means the distance between elements (padding, margins, gaps).

**Typography**

Typography is the way text looks — font size, weight, spacing.

Material Design defines a typography scale:

- h1 to h6 (headings)

- body1, body2 (paragraphs)

- caption, subtitle1

You use the ```<Typography>``` component with a ```variant``` prop.

**Motion (Animarion and Feedback)**

Motion is how UI elements move, animate, or respond to interactions.

Material Design says motion should:

- Show cause and effect

- Be smooth and intentional

- Help users understand what changed

Components like ```<Collapse>```, ```<Slide>```, ```<Fade>```, and ```<Grow>``` handle

**Color and Theme**



## Installing and Setting Up MUI in a React App

*create a react App*

```
npx create-react-app my-mui-app
cd my-mui-app
```

*Install MUI and Emotion Packages:*

```
npm install @mui/material @emotion/react @emotion/styled
```
*Installing Icons*

```
npm install @mui/icons-material
```


# Typography

used for styling text things like :
- Font size

- Font family

- Font weight (boldness)

- Line height

- Letter spacing

- Alignment

## Typography prop

**Variant**
 exmples h1,h2,body1.body2,caption,overline,button

 - components

 inplace of varinat you use it like a teller i have h3 , on variant but hi component
 
 - gutterBottom -used to add space below act like <br/>

 - align 

 - color

 - sx -style extension -for styling

  Example Default Typography:

|Variant	|Font Size|	Font Weight|
|--------|--------|-------|
|h1|	96px|	300|
|h2|	60px|	300|
|h3|	48px|	400|
|h4|	34px	|400|
|h5|	24px|	400|
|h6|	20px|	500|
|body1	|16px	|400|
|body2	|14px	|400|

## Button and icons

#### button -contain this variants

- text,contained,outline

## color prop

contain the following styling color

- primary,secondary,error,warning,info,success

## size prop

- small,medium large i.e sm,md,l,

**NOTE** <b>sx</b> used for inner responsive styling 

## Icons in MUI 

```
npm install @mui/icons-material
```

we have front and end icons

| Icon Position | Prop                   |
| ------------- | ---------------------- |
| Before text   | `startIcon={<Icon />}` |
| After text    | `endIcon={<Icon />}`   |

# Card and Containers

Card- is a rectangular container used to group related information like profile ,article,product or messege

a title,a short paragraph ,an image or icon ,a button or action *<Card/>*

*Components in card*
 
 | Component     | Purpose                            |
| ------------- | ---------------------------------- |
| `Card`        | The outer container                |
| `CardContent` | Holds the text                     |
| `CardMedia`   | Adds an image or video             |
| `CardActions` | Holds buttons                      |
| `Typography`  | Used for title, subtitle, and body |

#### What CardMedia props mean:


| Prop              | Purpose                        |
| ----------------- | ------------------------------ |
| `component="img"` | Tell MUI it's an image element |
| `height="140"`    | Height in px                   |
| `image="..."`     | URL of image                   |
| `alt="..."`       | Alt text (accessibility)       |



## Container

A Container is a layout component that centers and adds horizontal padding to your content.It’s commonly used to wrap the main body of your page.
```bash
<Container maxWidth="md" sx={{ py: 4 }}>
  <Grid container spacing={3}>
    <Grid item xs={12} sm={6} md={4}>
      <FullCard />
    </Grid>
    <Grid item xs={12} sm={6} md={4}>
      <FullCard />
    </Grid>
  </Grid>
</Container>
```

**maxwidth** it have this values 

| Value | Meaning                           |
| ----- | --------------------------------- |
| `xs`  | extra-small (up to 600px)         |
| `sm`  | small (up to 900px)               |
| `md`  | medium (up to 1200px) (default)   |
| `lg`  | large (up to 1536px)              |
| `xl`  | extra-large (max width unlimited) |

### Grid and Container

The Grid system is a flexible layout system based on a 12-column design.

You divide space like this:

- xs={12} → full width

- xs={6} → half

- xs={4} → 1/3

- xs={3} → 1/4

| Component          | Purpose                         |
| ---------------------|--------------------------------- |
| `<Grid container>` | The outer wrapper – it **holds rows**   |
| `<Grid item>`      | The columns or **cells inside the row** |

exmple 

```
import { Grid, Paper } from '@mui/material';

function TwoColumns() {
  return (
    <Grid container spacing={2}>
      <Grid item xs={6}>
        <Paper sx={{ p: 2 }}>Left Side</Paper>
      </Grid>
      <Grid item xs={6}>
        <Paper sx={{ p: 2 }}>Right Side</Paper>
      </Grid>
    </Grid>
  );
}
```
**Breakdown:**
container means this is a grid row

item means this is a column

xs={6} means 6 out of 12 columns → half width

spacing={2} adds space between columns

**exmple 2**
```
import { Container, Grid, Paper, Typography } from '@mui/material';

function GridLayoutExample() {
  return (
    <Container maxWidth="md" sx={{ mt: 4 }}>
      <Typography variant="h4" gutterBottom>
        My Grid Layout
      </Typography>

      <Grid container spacing={3}>
        <Grid item xs={12} sm={6} md={4}>
          <Paper sx={{ p: 2 }}>Item 1</Paper>
        </Grid>
        <Grid item xs={12} sm={6} md={4}>
          <Paper sx={{ p: 2 }}>Item 2</Paper>
        </Grid>
        <Grid item xs={12} sm={6} md={4}>
          <Paper sx={{ p: 2 }}>Item 3</Paper>
        </Grid>
      </Grid>
    </Container>
  );
}
```
You can also combine grid with cards and it work perfectly fine 

*spacing* add space

```
<Grid container spacing={3}>
  {Array.from(Array(6)).map((_, index) => (
    <Grid item xs={12} sm={6} md={4} key={index}>
      <Card>
        <CardContent>
          <Typography variant="h6">Card #{index + 1}</Typography>
          <Typography variant="body2">This is some content.</Typography>
        </CardContent>
      </Card>
    </Grid>
  ))}
</Grid>
```
# MUI GRID SYSTEM

The Material UI Grid system is a responsive layout system based on 12 columns, using Flexbox under the hood.Adjust layout per screen size (xs, sm, md, lg),

KEY APRTS OF Grid in MUI

| Component          | Role                                |
| ------------------ | ----------------------------------- |
| `<Grid container>` | Defines a **row** of items          |
| `<Grid item>`      | Defines a **column** inside the row |

**N/B** Remember to be using arrays.from or map to render cards in grid system just for easy readerbilty

## Stack in Mui and Spacing

A Stack in Material UI is a layout component that helps you place things in a row or column, and adds spacing between them automatically.

It’s like saying:

*“Put these buttons one below the other — and give me 20px between them — and don’t make me write CSS for it.”*
```
import Stack from '@mui/material/Stack';
```

**So by default, a Stack places elements vertically, with a configurable space between them.**

#### Spacing in stack

spacing is a prop you use to set the space between child components inside a Stack.

> *How It Works:
>
> The unit is based on the theme spacing. 

>In Material UI, 1 spacing unit = 8px.*

| Value | Pixels |
| ----- | ------ |
| `1`   | 8px    |
| `2`   | 16px   |
| `3`   | 24px   |
| `4`   | 32px   |

**What the sx properties mean**

| Prop      | Meaning                       |
| --------- | ----------------------------- |
| `p`       | Padding (inside the element)  |
| `m`       | Margin (outside the element)  |
| `px`      | Padding left + right          |
| `py`      | Padding top + bottom          |
| `mt`      | Margin top                    |
| `mb`      | Margin bottom                 |
| `bgcolor` | Background color (from theme) |
| `color`   | Text color (from theme)       |

#  Paper and Surface Components in Material UI

Paper is a surface component that gives a white (or themed) background with elevation (shadow) — like a sheet of paper.

It’s often used as a container that:

- Holds cards

- Wraps forms

- Creates panels or dialogs

- Visually separates content from the background

*why use paper*

| Problem Without Paper | Solved With Paper          |
| --------------------- | -------------------------- |
| Content looks flat    | Paper adds visual depth    |
| No padding or border  | Paper provides clean area  |
| Background may blend  | Paper separates background |

*think of Paper as the foundation for all UI blocks — cards, alerts, forms, dialogs,*

**Elevation** controls how much shadow depth the paper has. It makes the Paper look like it’s floating above the background.

| Value      | Visual Effect                  |
| ---------- | ------------------------------ |
| `0`        | No shadow (flat)               |
| `1`        | Small soft shadow              |
| `3`        | Moderate shadow (default look) |
| `10`, `24` | Very high/floating look        |

*N/B*  Maximum is 24 — use higher values for modal or dialog boxes.

**Combinning paper with Grid or stack**

```
<Stack spacing={3}>
  <Paper elevation={1} sx={{ p: 2 }}>
    <Typography variant="h6">Login Form</Typography>
    <TextField label="Email" fullWidth />
    <TextField label="Password" type="password" fullWidth />
    <Button variant="contained">Login</Button>
  </Paper>

  <Paper elevation={4} sx={{ p: 2, bgcolor: 'warning.light' }}>
    Warning Area
  </Paper>
</Stack>
``` 
#### when to use paper

| Use Case             | Why Use Paper?                                |
| -------------------- | --------------------------------------------- |
| Cards                | Add background and shadow for floating effect |
| Forms                | Give user input areas a clear container       |
| Alerts or messages   | Make them stand out from page background      |
| Dialog/Modal content | Create raised content above everything else   |
| Content sectioning   | Break page into sections visually             |

# Forms and Inputs TextField and Input Variants

*What Is a TextField?*

TextField is the main form input component in MUI used for typing text, emails, passwords, numbers, etc.an input field,a label,validation/error styling,and helper text — all in one.

**Textfield props**

| Prop         | What It Does                                                          |
| ------------ | --------------------------------------------------------------------- |
| `label`      | Adds a floating label inside the field                                |
| `variant`    | Controls style: `outlined`, `filled`, or `standard`  |
| `type`       | Defines input type: `text`, `email`, `password`, `number`, etc.       |
| `fullWidth`  | Makes the field stretch to 100% width of its container                |
| `value`      | Current value (for controlled input)                                  |
| `onChange`   | Function that handles typing changes                                  |
| `error`      | Boolean: makes field red when true                                    |
| `helperText` | Extra message under the input (e.g., “Must be at least 6 characters”) |

*controlled state inputs*

```
import { useState } from 'react';
import { TextField } from '@mui/material';

function MyForm() {
  const [name, setName] = useState('');

  return (
    <TextField
      label="Your Name"
      variant="outlined"
      value={name}
      onChange={(e) => setName(e.target.value)}
    />
  );
}
```
**how different input types-for password,numers,email used**

```
<TextField label="Password" type="password" />
<TextField label="Email" type="email" />
<TextField label="Age" type="number" />
```
**showing errors and helper text**

```
<TextField
  label="Email"
  type="email"
  error={true}
  helperText="This email is not valid."
/>
```
textarea eqivalent is multiline 

####  Select, Autocomplete, and Radio Buttons

Select is a dropdown input that lets the user pick one option from a list.

exmple
```
import { Select, MenuItem, FormControl, InputLabel } from '@mui/material';
import { useState } from 'react';

function GenderSelect() {
  const [gender, setGender] = useState('');

  return (
    <FormControl fullWidth>
      <InputLabel id="gender-label">Gender</InputLabel>
      <Select
        labelId="gender-label"
        id="gender"
        value={gender}
        onChange={(e) => setGender(e.target.value)}
        label="Gender"
      >
        <MenuItem value="male">Male</MenuItem>
        <MenuItem value="female">Female</MenuItem>
        <MenuItem value="other">Other</MenuItem>
      </Select>
    </FormControl>
  );
}
```

**Component Breakdown**

| Component     | Purpose                                 |
| ------------- | --------------------------------------- |
| `FormControl` | Wraps the field for layout and labeling |
| `InputLabel`  | Floating label linked by `labelId`      |
| `Select`      | Dropdown menu control                   |
| `MenuItem`    | Each choice inside the select           |

*Autocomplete*

Autocomplete is a more powerful select — it allows searching, typing, suggestions, and even free input if allowed.

```
import { Autocomplete, TextField } from '@mui/material';

const countries = ['Kenya', 'Tanzania', 'Uganda', 'Ethiopia'];

<Autocomplete
  options={countries}
  renderInput={(params) => (
    <TextField {...params} label="Country" variant="outlined" />
  )}
/>
```
*Explanation:*

| Prop          | Meaning                                      |
| ------------- | -------------------------------------------- |
| `options`     | List of available choices                    |
| `renderInput` | What the field looks like (uses `TextField`) |
| `{...params}` | Autocomplete passes props to your field      |
| `label="..."` | Label for the input field                    |

**Radio buttons**

Radio lets users pick only one option from a group. Like a Select, but visible on screen.

```
import {
  Radio,
  RadioGroup,
  FormControl,
  FormControlLabel,
  FormLabel
} from '@mui/material';

<FormControl>
  <FormLabel id="job-type">Job Type</FormLabel>
  <RadioGroup
    aria-labelledby="job-type"
    value={job}
    onChange={(e) => setJob(e.target.value)}
    name="job"
    row
  >
    <FormControlLabel value="full" control={<Radio />} label="Full-Time" />
    <FormControlLabel value="part" control={<Radio />} label="Part-Time" />
    <FormControlLabel value="freelance" control={<Radio />} label="Freelance" />
  </RadioGroup>
</FormControl>
```

*Explanation*

| Component          | Purpose                                  |
| ------------------ | ---------------------------------------- |
| `FormControl`      | Groups label + radio group together      |
| `FormLabel`        | Title for the radio group                |
| `RadioGroup`       | Manages the selected value               |
| `FormControlLabel` | Wraps each Radio with a label            |
| `Radio`            | The circular selectable input            |
| `row`              | Layout: makes radios appear side by side |

**important imports**
```
import Radio from '@mui/material/Radio';
import RadioGroup from '@mui/material/RadioGroup';
import FormControl from '@mui/material/FormControl';
import FormControlLabel from '@mui/material/FormControlLabel';
import FormLabel from '@mui/material/FormLabel';
```

#### Checkbox,Switch and Skiders

A checkbox lets users choose yes/no, true/false, or select multiple options.

```
import Checkbox from '@mui/material/Checkbox';
import FormControlLabel from '@mui/material/FormControlLabel';
import FormGroup from '@mui/material/FormGroup';
```

**A Switch** is like a checkbox, but styled like a mobile on/off toggle.

- Used for settings like:

- Dark mode 🌙 / Light mode ☀️

- Notifications: On / Off

- Enable / Disable account

```
const [darkMode, setDarkMode] = useState(false);

<FormControlLabel
  control={
    <Switch
      checked={darkMode}
      onChange={(e) => setDarkMode(e.target.checked)}
    />
  }
  label="Enable Dark Mode"
/>
```

**A slider** lets the user select a number or range of values by sliding a thumb left and right.e.g voumen control,price filter range and ratings or weights.

```
const [volume, setVolume] = useState(30);

<Slider
  value={volume}
  onChange={(e, newValue) => setVolume(newValue)}
  aria-label="Volume"
  valueLabelDisplay="auto"
  min={0}
  max={100}
/>
```
```
<Divider sx={{ my: 2 }} />

```
 for creating a horizontal line

**n/b** control is used when working with formcontrollabel but you can use the components such as chechbox,radio button e.t.c alone

### FormControl and FormGroup.

FormControl is a wrapper component that groups together form inputs and their labels, making sure they are styled, aligned, and accessible correctly in Material UI.

**Why Use FormControl?**

Connects inputs and labels correctly for screen readers (accessibility)

Helps handle error state, helper text, disabled state

Ensures consistent spacing and alignment

Works behind the scenes to coordinate MUI form behaviors

*props in formcontrol*

| Prop        | Meaning                                                          |
| ----------- | ---------------------------------------------------------------- |
| `fullWidth` | Makes the input stretch to fill 100% of its parent               |
| `disabled`  | Disables all child inputs automatically                          |
| `error`     | Shows error styling (red underline, red label)                   |
| `required`  | Adds an asterisk (\*) to label to show it’s required             |
| `variant`   | Sets the style (standard, outlined, filled — passed to children) |

exmple 

```
import {
  FormControl,
  InputLabel,
  Select,
  MenuItem,
} from '@mui/material';

<FormControl fullWidth>
  <InputLabel id="language-label">Language</InputLabel>
  <Select labelId="language-label" defaultValue="">
    <MenuItem value="en">English</MenuItem>
    <MenuItem value="fr">French</MenuItem>
    <MenuItem value="sw">Swahili</MenuItem>
  </Select>
</FormControl>
```

**FormGroup** is a container that holds a group of related inputs, like checkboxes or switches, and lays them out vertically or horizontally.

It is useful when:

- You have multiple checkboxes or switches

- You want to organize them cleanly

- You want to group them under one label or heading

Example:for uncontrolled states

```
import {
  FormGroup,
  FormControlLabel,
  Checkbox,
  Typography,
} from '@mui/material';

<FormGroup>
  <Typography variant="subtitle1">Choose Interests</Typography>
  <FormControlLabel control={<Checkbox defaultChecked />} label="Music" />
  <FormControlLabel control={<Checkbox />} label="Movies" />
  <FormControlLabel control={<Checkbox />} label="Coding" />
</FormGroup>
```
Explanation

| Component          | Purpose                              |
| ------------------ | ------------------------------------ |
| `FormGroup`        | Arranges the checkboxes together     |
| `FormControlLabel` | Binds label and input together       |
| `Checkbox`         | The actual input (uncontrolled here) |

*props for formgroup*

| Prop  | What It Does                                                     |
| ----- | ---------------------------------------------------------------- |
| `row` | If true, aligns all items **horizontally** instead of vertically |

**Difference between FormControls and FormGroup**

| Feature                        | `FormControl`                       | `FormGroup`                       |
| ------------------------------ | ----------------------------------- | --------------------------------- |
| Purpose                        | Wraps a single field with logic     | Wraps a set of similar inputs     |
| Use Case                       | `Select`, `TextField`, `RadioGroup` | `Checkbox`, `Switch` collections  |
| Layout feature                 | No layout styling                   | Has layout (`row`, spacing, etc.) |
| Props like `error`, `required` | ✅ Yes                               | ❌ No (handled per checkbox)       |

*Exmple with controlled state*

```
const [skills, setSkills] = useState({
  html: false,
  css: true,
  js: false,
});

const handleSkillChange = (e) => {
  const { name, checked } = e.target;
  setSkills((prev) => ({
    ...prev,
    [name]: checked,
  }));
};

<FormControl component="fieldset">
  <Typography variant="h6">Your Skills</Typography>
  <FormGroup row>
    <FormControlLabel
      control={
        <Checkbox
          name="html"
          checked={skills.html}
          onChange={handleSkillChange}
        />
      }
      label="HTML"
    />
    <FormControlLabel
      control={
        <Checkbox
          name="css"
          checked={skills.css}
          onChange={handleSkillChange}
        />
      }
      label="CSS"
    />
    <FormControlLabel
      control={
        <Checkbox
          name="js"
          checked={skills.js}
          onChange={handleSkillChange}
        />
      }
      label="JavaScript"
    />
  </FormGroup>
</FormControl>
```
*Explannation*

| Element            | Role                                                    |
| ------------------ | ------------------------------------------------------- |
| `FormControl`      | Wraps label + group of checkboxes                       |
| `FormGroup`        | Arranges inputs (row or column)                         |
| `FormControlLabel` | Ties `Checkbox` to a label                              |
| `Checkbox`         | The actual input (controlled via state)                 |
| `name="js"`        | Used in `handleSkillChange` to know which key to update |
| `onChange={...}`   | Updates the object state (`html`, `css`, `js`)          |


#  Handling Form State (with Formik or React Hook Form)

**what is Formik?**

Formik is a small library that helps you build forms in React easily, by handling:i.e Formik is a tool that helps you build and manage forms in React without writing too much code.

- State (like useState does)

- Validation

- Submission

- Error handling

- Touch tracking (was this field edited?)

**Why Was Formik Created?**

In regular React:

- You manage every form input with useState

- You write custom onChange, onBlur, onSubmit

- You write your own validation logic

That works... but for big forms, it becomes:

❌ Messy
❌ Hard to validate
❌ Lots of duplicate code
❌ Tedious for multiple inputs

📦 Formik was created to make form logic easy and automatic.

Installation:
```
npm install formik
```

If you want to use validation, also install:

```
npm install yup
```
**yup** is a validation library (like grammar rules for form data).
Formik doesn’t validate by itself — it lets you use libraries like Yup for that.

[formik](https://formik.org/)

Example

```
import React from 'react';
import { Formik } from 'formik';

const Basic = () => (
  <div>
    <h1>Anywhere in your app!</h1>
    <Formik
      initialValues={{ email: '', password: '' }}
      validate={values => {
        const errors = {};
        if (!values.email) {
          errors.email = 'Required';
        } else if (
          !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
        ) {
          errors.email = 'Invalid email address';
        }
        return errors;
      }}
      onSubmit={(values, { setSubmitting }) => {
        setTimeout(() => {
          alert(JSON.stringify(values, null, 2));
          setSubmitting(false);
        }, 400);
      }}
    >
      {({
        values,
        errors,
        touched,
        handleChange,
        handleBlur,
        handleSubmit,
        isSubmitting,
        /* and other goodies */
      }) => (
        <form onSubmit={handleSubmit}>
          <input
            type="email"
            name="email"
            onChange={handleChange}
            onBlur={handleBlur}
            value={values.email}
          />
          {errors.email && touched.email && errors.email}
          <input
            type="password"
            name="password"
            onChange={handleChange}
            onBlur={handleBlur}
            value={values.password}
          />
          {errors.password && touched.password && errors.password}
          <button type="submit" disabled={isSubmitting}>
            Submit
          </button>
        </form>
      )}
    </Formik>
  </div>
);

export default Basic;
```

**Reducing boilerplate**

The code above is very explicit about exactly what Formik is doing. onChange -> handleChange, onBlur -> handleBlur, and so on. However, to save you time, Formik comes with a few extra components to make life easier and less verbose: <Form />, <Field />, and <ErrorMessage />. They use React context to hook into the parent <Formik /> state/methods.

Exmple:

```
// Render Prop
import React from 'react';
import { Formik, Form, Field, ErrorMessage } from 'formik';

const Basic = () => (
  <div>
    <h1>Any place in your app!</h1>
    <Formik
      initialValues={{ email: '', password: '' }}
      validate={values => {
        const errors = {};
        if (!values.email) {
          errors.email = 'Required';
        } else if (
          !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
        ) {
          errors.email = 'Invalid email address';
        }
        return errors;
      }}
      onSubmit={(values, { setSubmitting }) => {
        setTimeout(() => {
          alert(JSON.stringify(values, null, 2));
          setSubmitting(false);
        }, 400);
      }}
    >
      {({ isSubmitting }) => (
        <Form>
          <Field type="email" name="email" />
          <ErrorMessage name="email" component="div" />
          <Field type="password" name="password" />
          <ErrorMessage name="password" component="div" />
          <button type="submit" disabled={isSubmitting}>
            Submit
          </button>
        </Form>
      )}
    </Formik>
  </div>
);

export default Basic;
```

**Core Concept in Formik**

| Term               | What It Means                                                                |
| ------------------ | ---------------------------------------------------------------------------- |
| `initialValues`    | The starting/default values for your form fields                             |
| `validationSchema` | A `Yup` object that defines rules for each field (e.g., email must be valid) |
| `onSubmit`         | Function to run when the form is submitted                                   |
| `handleChange`     | Function that updates the field's value (same as `onChange`)                 |
| `handleBlur`       | Marks the field as "touched" (used for when to show error messages)          |
| `handleSubmit`     | Function that handles form submission logic                                  |
| `values`           | An object containing all the current values entered by the user              |
| `errors`           | Object containing validation errors                                          |
| `touched`          | Tracks which fields the user has interacted with                             |

Example with full core componets:

```
import { Formik } from 'formik';
import * as Yup from 'yup';
import { TextField, Button, Typography } from '@mui/material';

<Formik
  initialValues={{ name: '', email: '' }}
  validationSchema={Yup.object({
    name: Yup.string().required('Name is required'),
    email: Yup.string().email('Invalid email').required('Email is required'),
  })}
  onSubmit={(values) => {
    console.log(values); // handle your data
  }}
>
  {({
    handleSubmit,
    handleChange,
    handleBlur,
    values,
    errors,
    touched,
  }) => (
    <form onSubmit={handleSubmit}>
      <TextField
        name="name"
        label="Name"
        value={values.name}
        onChange={handleChange}
        onBlur={handleBlur}
        error={touched.name && Boolean(errors.name)}
        helperText={touched.name && errors.name}
        fullWidth
        margin="normal"
      />

      <TextField
        name="email"
        label="Email"
        value={values.email}
        onChange={handleChange}
        onBlur={handleBlur}
        error={touched.email && Boolean(errors.email)}
        helperText={touched.email && errors.email}
        fullWidth
        margin="normal"
      />

      <Button type="submit" variant="contained">
        Submit
      </Button>
    </form>
  )}
</Formik>
```

Example 2

```
import React from 'react';
import { Formik } from 'formik';
import * as Yup from 'yup';
import {
  TextField,
  Checkbox,
  Switch,
  Slider,
  FormControlLabel,
  Button,
  Box,
  Paper,
  Typography,
  Divider,
} from '@mui/material';

const PreferencesForm = () => {
  return (
    <Paper elevation={3} sx={{ maxWidth: 500, mx: 'auto', mt: 5, p: 4 }}>
      <Typography variant="h5" gutterBottom>
        User Preferences
      </Typography>

      <Formik
        initialValues={{
          fullName: '',
          subscribe: false,
          notifications: true,
          volume: 30,
        }}
        validationSchema={Yup.object({
          fullName: Yup.string()
            .min(2, 'Too short')
            .required('Full Name is required'),
        })}
        onSubmit={(values) => {
          console.log('Submitted Values:', values);
        }}
      >
        {({
          values,
          handleChange,
          handleBlur,
          handleSubmit,
          setFieldValue,
          touched,
          errors,
        }) => (
          <form onSubmit={handleSubmit}>
            {/* TextField */}
            <TextField
              fullWidth
              label="Full Name"
              name="fullName"
              value={values.fullName}
              onChange={handleChange}
              onBlur={handleBlur}
              error={touched.fullName && Boolean(errors.fullName)}
              helperText={touched.fullName && errors.fullName}
              margin="normal"
            />

            {/* Checkbox */}
            <FormControlLabel
              control={
                <Checkbox
                  name="subscribe"
                  checked={values.subscribe}
                  onChange={handleChange}
                />
              }
              label="Subscribe to newsletter"
            />

            {/* Switch */}
            <FormControlLabel
              control={
                <Switch
                  name="notifications"
                  checked={values.notifications}
                  onChange={handleChange}
                />
              }
              label="Enable Notifications"
            />

            <Divider sx={{ my: 3 }} />

            {/* Slider */}
            <Typography gutterBottom>
              Volume: {values.volume}%
            </Typography>
            <Slider
              name="volume"
              value={values.volume}
              onChange={(e, val) => setFieldValue('volume', val)}
              min={0}
              max={100}
              step={10}
              valueLabelDisplay="auto"
            />

            <Button
              type="submit"
              variant="contained"
              color="primary"
              fullWidth
              sx={{ mt: 3 }}
            >
              Save Preferences
            </Button>
          </form>
        )}
      </Formik>
    </Paper>
  );
};

export default PreferencesForm;
```

**React Hook Form**

React Hook Form (RHF) is a library that lets you build and validate forms in React with less code and better performance.

It uses:

- React hooks (useForm, Controller)

- Smart re-rendering logic

- Works with any UI library, including Material UI

*comparison with formik*

| Feature     | Formik                                 | React Hook Form                        |
| ----------- | -------------------------------------- | -------------------------------------- |
| Re-renders  | More (every change triggers re-render) | Fewer (re-renders only changed inputs) |
| Setup       | Easy but more verbose                  | Minimal, clean, efficient              |
| Validation  | Yup (external)                         | Yup (also supported)                   |
| Performance | Slower in large forms                  | Faster and more scalable               |
| Integration | Manual binding                         | Use `Controller` for external inputs   |

```
npm install react-hook-form
npm install @hookform/resolvers yup
```

*Core concepts in RHF*

| Term             | Meaning                                                           |
| ---------------- | ----------------------------------------------------------------- |
| `useForm()`      | Hook that creates and manages the form                            |
| `register()`     | Connects native HTML inputs to RHF                                |
| `Controller`     | Connects **external inputs** like Material UI (TextField, Slider) |
| `handleSubmit()` | Function that processes form submission                           |
| `formState`      | Gives you access to `errors`, `touchedFields`, `isDirty`, etc.    |
| `setValue()`     | Allows manual setting of field values                             |

Example:

```
import {
  useForm,
  Controller
} from 'react-hook-form';
import {
  TextField,
  Checkbox,
  Switch,
  Slider,
  Button,
  FormControlLabel,
  Paper,
  Typography,
  Divider,
} from '@mui/material';
import { yupResolver } from '@hookform/resolvers/yup';
import * as Yup from 'yup';

const validationSchema = Yup.object({
  fullName: Yup.string().required('Full name is required'),
});

export default function RHFForm() {
  const {
    control,
    handleSubmit,
    register,
    formState: { errors }
  } = useForm({
    defaultValues: {
      fullName: '',
      subscribe: false,
      notifications: true,
      volume: 40
    },
    resolver: yupResolver(validationSchema)
  });

  const onSubmit = (data) => {
    console.log('Submitted:', data);
  };

  return (
    <Paper elevation={4} sx={{ p: 4, maxWidth: 500, mx: 'auto', mt: 5 }}>
      <Typography variant="h5" gutterBottom>
        React Hook Form - User Preferences
      </Typography>

      <form onSubmit={handleSubmit(onSubmit)}>

        {/* TextField */}
        <Controller
          name="fullName"
          control={control}
          render={({ field }) => (
            <TextField
              label="Full Name"
              fullWidth
              margin="normal"
              {...field}
              error={Boolean(errors.fullName)}
              helperText={errors.fullName?.message}
            />
          )}
        />

        {/* Checkbox */}
        <Controller
          name="subscribe"
          control={control}
          render={({ field }) => (
            <FormControlLabel
              control={<Checkbox {...field} checked={field.value} />}
              label="Subscribe to newsletter"
            />
          )}
        />

        {/* Switch */}
        <Controller
          name="notifications"
          control={control}
          render={({ field }) => (
            <FormControlLabel
              control={<Switch {...field} checked={field.value} />}
              label="Enable Notifications"
            />
          )}
        />

        <Divider sx={{ my: 3 }} />

        {/* Slider */}
        <Typography gutterBottom>
          Volume: <strong>{control._formValues.volume}%</strong>
        </Typography>
        <Controller
          name="volume"
          control={control}
          render={({ field }) => (
            <Slider
              value={field.value}
              onChange={(_, val) => field.onChange(val)}
              min={0}
              max={100}
              step={10}
              valueLabelDisplay="auto"
            />
          )}
        />

        <Button type="submit" variant="contained" fullWidth sx={{ mt: 3 }}>
          Submit Preferences
        </Button>
      </form>
    </Paper>
  );
}
```

# Navigation Components 

**AppBar and ToolBar**

*AppBar* is a Material UI component used to create a top bar in your application — like a navigation header or site title bar.

It usually contains:

- The site title or logo

- Navigation buttons (like “Home”, “Profile”)

- Sometimes menus, icons, or a search bar

Think of it like the "top bar" you see in all apps or websites.

**Toolbar** is a flexible container inside the AppBar used to align and space its content (like title, buttons, menus, etc.).

It behaves like a box that arranges children horizontally, with padding and spacing.

Example:

```
import { AppBar, Toolbar, Typography } from '@mui/material';

<AppBar position="static">
  <Toolbar>
    <Typography variant="h6">
      My App
    </Typography>
  </Toolbar>
</AppBar>
```

| Component    | Purpose                                             |
| ------------ | --------------------------------------------------- |
| `AppBar`     | Main top bar container (like a nav wrapper)         |
| `position`   | Controls if it’s fixed, sticky, absolute, or static |
| `Toolbar`    | Holds the actual content (title, icons, buttons)    |
| `Typography` | Used here as the app’s title (like `<h1>`)          |

**Properties**

postion prop: staic,fixed,absolute,sticky

color prop:primary,secondary,inherit,transparent


**Drawer (Sidebar Navigation)**

A Drawer is a panel (like a sidebar) that slides in from the side of the screen.
It's used for navigation or menu content, especially on mobile or dashboard apps.

*Components*

| Component                    | Role                                              |
| ---------------------------- | ------------------------------------------------- |
| `Drawer`                     | The sliding panel itself                          |
| `List`                       | Wraps all menu items                              |
| `ListItem`, `ListItemButton` | Each row inside the drawer (like “Home”, “About”) |
| `ListItemText`               | The label inside the row                          |
| `IconButton`                 | The menu button (usually in the AppBar)           |
| `MenuIcon`                   | The hamburger icon (☰)                            |


*Types of Drawer (Controlled by variant prop)*

Material UI gives three types of Drawer based on how they behave:

| Variant      | Behavior                                                            |
| ------------ | ------------------------------------------------------------------- |
| `temporary`  | Slides over the page. Disappears when user clicks outside (default) |
| `permanent`  | Always visible. Used in dashboards (like Gmail sidebar)             |
| `persistent` | Slides in and **stays open** until manually closed                  |

```
<Drawer variant="temporary" />
<Drawer variant="permanent" />
<Drawer variant="persistent" />
```
*Props for Drawer*

| Prop         | Type       | Description                                                              |       |            |                                  |
| ------------ | ---------- | ------------------------------------------------------------------------ | ----- | ---------- | -------------------------------- |
| `anchor`     | \`'left'   | 'right'                                                                  | 'top' | 'bottom'\` | Side from which drawer slides in |
| `open`       | `boolean`  | Controls whether drawer is open or not (used with state)                 |       |            |                                  |
| `onClose`    | `function` | Function called when drawer should close (like when clicking background) |       |            |                                  |
| `variant`    | string     | `"temporary"` (default), `"persistent"`, or `"permanent"`                |       |            |                                  |
| `sx`         | object     | Inline styling (background, width, etc.)                                 |       |            |                                  |
| `PaperProps` | object     | Style the inside surface of the drawer (`backgroundColor`, etc.)         |       |            |                                  |

*What Components Go Inside a Drawer*

| Component        | Use                                       |
| ---------------- | ----------------------------------------- |
| `Box`            | Wraps the content and sets drawer width   |
| `List`           | Vertical container for navigation links   |
| `ListItem`       | Represents one row (like one link)        |
| `ListItemButton` | Makes `ListItem` clickable                |
| `ListItemIcon`   | Adds an icon to the left of the text      |
| `ListItemText`   | Displays the label (like “Home”, “About”) |

**Styling Drawer**
```
<Drawer
  sx={{ '& .MuiDrawer-paper': { width: 250, backgroundColor: '#111' } }}
  open={open}
>
```
- *& .MuiDrawer*-paper targets the inner part (the sliding sheet)

- You can also use PaperProps to style:

```
<Drawer PaperProps={{ sx: { backgroundColor: 'blue' } }} />
```
To show/hide the drawer ,you use react state

```
const [open, setOpen] = useState(false);

// open
setOpen(true);

// close (e.g., after clicking background)
setOpen(false);
```
 Then pass the states 

 ```
 <Drawer open={open} onClose={() => setOpen(false)} />
```

Example

```bash
import React, { useState } from 'react';
import {
  AppBar,
  Toolbar,
  Typography,
  IconButton,
  Drawer,
  List,
  ListItem,
  ListItemButton,
  ListItemText,
  Box,
} from '@mui/material';
import MenuIcon from '@mui/icons-material/Menu';

export default function SidebarDrawer() {
  const [open, setOpen] = useState(false); // state controls visibility
  const menuItems = ['Home', 'About', 'Portfolio', 'Contact'];

  return (
    <>
      {/* Top Navigation Bar */}
      <AppBar position="static">
        <Toolbar>
          <IconButton edge="start" color="inherit" onClick={() => setOpen(true)}>
            <MenuIcon />
          </IconButton>

          <Typography variant="h6" sx={{ flexGrow: 1 }}>
            MySite
          </Typography>
        </Toolbar>
      </AppBar>

      {/* Drawer (Sidebar) */}
      <Drawer
        anchor="left"
        open={open}
        onClose={() => setOpen(false)}
        PaperProps={{
          sx: { width: 250, backgroundColor: '#f4f4f4' },
        }}
      >
        <Box role="presentation" onClick={() => setOpen(false)}>
          <List>
            {menuItems.map((text) => (
              <ListItem key={text} disablePadding>
                <ListItemButton>
                  <ListItemText primary={text} />
                </ListItemButton>
              </ListItem>
            ))}
          </List>
        </Box>
      </Drawer>
    </>
  );
}
```

**What Is BottomNavigation?**

BottomNavigation is a horizontal bar placed at the bottom of the screen that lets users switch between different views or sections — like tabs for mobile apps.

*Related Components in BottomNavigation*

| Component                | Purpose                                     |
| ------------------------ | ------------------------------------------- |
| `BottomNavigation`       | The main bar container                      |
| `BottomNavigationAction` | Represents one tab (e.g., "Home", "Search") |

*props for BottomNavigation*

| Prop         | Type     | Description                                                         |
| ------------ | -------- | ------------------------------------------------------------------- |
| `value`      | number   | The index of the selected tab                                       |
| `onChange`   | function | Called when a tab is clicked. You update the state                  |
| `showLabels` | boolean  | If true, labels are always shown. If false, only show when selected |

*props for BottomNavigationAction*

| Prop    | Type          | Description                      |
| ------- | ------------- | -------------------------------- |
| `label` | string        | The name under the icon          |
| `icon`  | ReactNode     | Usually a Material Icon          |
| `value` | string/number | Optional ID of this action       |
| `sx`    | object        | For styling spacing, color, etc. |

**What are TABS**

Tabs allow users to switch between different sections of content on the same page — usually seen at the top of a card, panel, or view.

What Tabs Do:

- Show multiple sections under a single view

- Only one section is visible at a time

- Clicking a tab updates the visible content

*Related Components for Tabs*

| Component  | Role                                           |
| ---------- | ---------------------------------------------- |
| `Tabs`     | Wraps all tab labels                           |
| `Tab`      | Represents each clickable tab                  |
| `TabPanel` | (Manual) A box to hold the content under a tab |
| `Box`      | Used for layout and spacing                    |

**important Props for Tabs**

| Prop             | Description                                           |
| ---------------- | ----------------------------------------------------- |
| `value`          | Which tab is currently selected (a number)            |
| `onChange`       | Function called when tab changes                      |
| `indicatorColor` | Color of the underline under active tab               |
| `textColor`      | Color of tab text (`inherit`, `primary`, `secondary`) |

*Exmple:Combined tabs and BottomNavigation*

```bash
import React, { useState } from 'react';
import {
  Tabs,
  Tab,
  Box,
  Typography,
  BottomNavigation,
  BottomNavigationAction,
  Paper
} from '@mui/material';
import HomeIcon from '@mui/icons-material/Home';
import PersonIcon from '@mui/icons-material/Person';
import SettingsIcon from '@mui/icons-material/Settings';

export default function TabAndBottomNavExample() {
  const [tabIndex, setTabIndex] = useState(0);
  const [bottomNav, setBottomNav] = useState(0);

  return (
    <>
      {/* Tabs at the Top */}
      <Box sx={{ width: '100%', bgcolor: 'background.paper' }}>
        <Tabs value={tabIndex} onChange={(e, newVal) => setTabIndex(newVal)} centered>
          <Tab label="Posts" />
          <Tab label="Media" />
          <Tab label="Mentions" />
        </Tabs>

        {tabIndex === 0 && <TabPanel>Posts content</TabPanel>}
        {tabIndex === 1 && <TabPanel>Media content</TabPanel>}
        {tabIndex === 2 && <TabPanel>Mentions content</TabPanel>}
      </Box>

      {/* Bottom Navigation */}
      <Paper sx={{ position: 'fixed', bottom: 0, left: 0, right: 0 }} elevation={3}>
        <BottomNavigation
          value={bottomNav}
          onChange={(e, newVal) => setBottomNav(newVal)}
          showLabels
        >
          <BottomNavigationAction label="Home" icon={<HomeIcon />} />
          <BottomNavigationAction label="Profile" icon={<PersonIcon />} />
          <BottomNavigationAction label="Settings" icon={<SettingsIcon />} />
        </BottomNavigation>
      </Paper>
    </>
  );
}

// TabPanel: simple content wrapper
function TabPanel({ children }) {
  return (
    <Box sx={{ p: 3 }}>
      <Typography>{children}</Typography>
    </Box>
  );
}
```

##### What Are Breadcrumbs?

Breadcrumbs are a navigation aid that shows users their current location in a site's hierarchy — like a trail that shows where you came from.

Example:

You might see this on a shopping site like Amazon:

```
Home / Electronics / Computers / Laptops
```

Each part is clickable, helping the user navigate back to higher-level categories.

*Why Use Breadcrumbs?*

- Show users where they are inside your app

- Let them easily go back to a parent page

- Helps with SEO and accessibility too

**Components involved in Breadcrumbs**

| Component          | Role                                              |
| ------------------ | ------------------------------------------------- |
| `Breadcrumbs`      | The wrapper that handles the layout and separator |
| `Link` (MUI)       | Used for clickable items (e.g. “Home”)            |
| `Typography`       | Used for the **current page** (non-clickable)     |
| `NavigateNextIcon` | The arrow used as the default separator (>)       |

*Props for Breadcrumbs*

| Prop                  | Type        | Description                                              |
| --------------------- | ----------- | -------------------------------------------------------- |
| `separator`           | node/string | What to show between items (default is `/` or `>` icon)  |
| `aria-label`          | string      | Used for accessibility (e.g. `"breadcrumb"`)             |
| `maxItems`            | number      | Collapses items if too many (e.g., shows `...`)          |
| `itemsBeforeCollapse` | number      | How many to show before collapse (if `maxItems` is used) |
| `itemsAfterCollapse`  | number      | How many to show after the collapse                      |

Example:

```
import React from 'react';
import { Breadcrumbs, Link, Typography } from '@mui/material';
import NavigateNextIcon from '@mui/icons-material/NavigateNext';

export default function BreadcrumbNav() {
  return (
    <Breadcrumbs
      separator={<NavigateNextIcon fontSize="small" />}
      aria-label="breadcrumb"
    >
      <Link underline="hover" color="inherit" href="/">
        Home
      </Link>
      <Link underline="hover" color="inherit" href="/blog">
        Blog
      </Link>
      <Link underline="hover" color="inherit" href="/blog/articles">
        Articles
      </Link>
      <Typography color="text.primary">How to Use Breadcrumbs</Typography>
    </Breadcrumbs>
  );
}
```

*note:* You can change separator to anything

```
separator="•"   // bullet
separator="→"   // arrow
```

##### Link and ButtonLink Usage in Material UI

**link**

Material UI’s Link is a component used to create text-based navigation links that look like normal links but are styled using Material UI's theme. It’s like an improved <a> tag with theme awareness and better styling.

*You can use it for:*

- Navigating between pages (using href)

- Navigating inside an app (with React Router)

- Styling links that look consistent with the Material theme

**Note** Don’t confuse it with React Router’s Link!

| `@mui/material/Link`    | Use for **style + links**                       |
| ----------------------- | ----------------------------------------------- |
| `react-router-dom/Link` | Use for **client-side routing** in React Router |

*All Important Props for MUI Link*

| Prop        | Type      | Purpose                                                          |
| ----------- | --------- | ---------------------------------------------------------------- |
| `href`      | string    | Destination path (like in `<a href="">`)                         |
| `underline` | string    | `'always'`, `'hover'`, `'none'` — controls how underline appears |
| `color`     | string    | `'primary'`, `'secondary'`, `'inherit'`, `'textPrimary'`, etc.   |
| `component` | ReactType | Allows replacing it with `react-router-dom`'s `Link` for routing |
| `sx`        | object    | Style overrides (padding, margin, fontSize, etc.)                |

**How to Make MUI Link Work With React Router?**

If you're using React Router, and want a client-side link (no page reload), you need to do:

```
import { Link as RouterLink } from 'react-router-dom';
import { Link as MUILink } from '@mui/material';

<MUILink component={RouterLink} to="/about">
  Go to About
</MUILink>
```

**What Is a “ButtonLink”?**

A ButtonLink is not a special component — it’s simply using a Button as a link by setting the component="a" or component={RouterLink}.

```
<Button component="a" href="/docs">
  Docs
</Button>
```

Or, with React Router:

```
<Button component={RouterLink} to="/contact">
  Contact
</Button>
```

 *Why Use ButtonLink?*

You want the look of a button, but it should behave like a link

Ideal for navigation menus, call-to-actions, etc.

Example:

```
import React from 'react';
import { Link as RouterLink } from 'react-router-dom';
import { Link, Button, Stack } from '@mui/material';

export default function LinkExample() {
  return (
    <Stack spacing={2}>
      {/* Text-style link using href */}
      <Link href="/home" underline="hover" color="primary">
        Go to Home (classic link)
      </Link>

      {/* Text-style link using React Router */}
      <Link component={RouterLink} to="/about" color="secondary" underline="always">
        About Page (router link)
      </Link>

      {/* Button that acts as a link (with href) */}
      <Button variant="contained" component="a" href="/docs">
        View Docs
      </Button>

      {/* Button link using React Router */}
      <Button variant="outlined" component={RouterLink} to="/contact">
        Contact Us
      </Button>
    </Stack>
  );
}
```

#  Feedback and UI Elements

#### Dialog (Modal) in Material UI
A Dialog is a popup (modal) window that appears on top of your content to show important information or ask for a decision.

*n/b* It blocks interaction with the rest of the UI until the user closes it or responds.

UseCases:

| Use Case                           | Dialog Purpose              |
| ---------------------------------- | --------------------------- |
| “Are you sure you want to delete?” | Confirmation prompt         |
| “Login / Sign Up”                  | Shows a form inside a popup |
| “Your session has expired”         | Notification of status      |

**Components Used in a Dialog**

| Component           | Purpose                                         |
| ------------------- | ----------------------------------------------- |
| `Dialog`            | Main wrapper for the popup/modal                |
| `DialogTitle`       | Title bar at the top                            |
| `DialogContent`     | Main area inside the dialog — text, forms, etc. |
| `DialogActions`     | Bottom row for buttons like “Cancel” or “OK”    |
| `DialogContentText` | Optional helper text within `DialogContent`     |

You can use any material ui component inside the dialog component

**Main prop for Dialog**

| Prop         | Type       | What It Does                                          |                                         |      |      |         |                      |
| ------------ | ---------- | ----------------------------------------------------- | --------------------------------------- | ---- | ---- | ------- | -------------------- |
| `open`       | `boolean`  | Controls whether the dialog is visible                |                                         |      |      |         |                      |
| `onClose`    | `function` | Called when user clicks outside or hits Escape        |                                         |      |      |         |                      |
| `fullWidth`  | `boolean`  | Makes dialog take full width of its container         |                                         |      |      |         |                      |
| `maxWidth`   | \`'xs'     | 'sm'                                                  | 'md'                                    | 'lg' | 'xl' | false\` | Controls dialog size |
| `fullScreen` | `boolean`  | If true, dialog fills entire screen (good for mobile) |                                         |      |      |         |                      |
| `scroll`     | \`'body'   | 'paper'\`                                             | Determines scrolling area inside dialog |      |      |         |                      |
| `PaperProps` | `object`   | To style the dialog paper (e.g., backgroundColor)     |                                         |      |      |         |                      |

*Dialod | Modal | Alert*

| Term   | Meaning                                                         |
| ------ | --------------------------------------------------------------- |
| Modal  | Any UI element that blocks the background                       |
| Dialog | A type of modal used for structured interaction (form, confirm) |
| Alert  | Simple notification — often non-blocking (e.g. Snackbar)        |

Example:Controlled

```
import React, { useState } from 'react';
import {
  Button,
  Dialog,
  DialogTitle,
  DialogContent,
  DialogContentText,
  DialogActions,
} from '@mui/material';

export default function ConfirmDialog() {
  const [open, setOpen] = useState(false);

  const handleOpen = () => setOpen(true);
  const handleClose = () => setOpen(false);
  const handleConfirm = () => {
    alert('Item deleted!');
    setOpen(false);
  };

  return (
    <>
      <Button variant="contained" color="error" onClick={handleOpen}>
        Delete
      </Button>

      <Dialog open={open} onClose={handleClose}>
        <DialogTitle>Confirm Delete</DialogTitle>
        <DialogContent>
          <DialogContentText>
            Are you sure you want to delete this item? This action cannot be undone.
          </DialogContentText>
        </DialogContent>
        <DialogActions>
          <Button onClick={handleClose} color="primary">
            Cancel
          </Button>
          <Button onClick={handleConfirm} color="error" autoFocus>
            Delete
          </Button>
        </DialogActions>
      </Dialog>
    </>
  );
}
```
#### Snackbar and Alerts in Material UI

**What is Snackbar**

A Snackbar is a small popup bar (usually at the bottom of the screen) that shows short messages or notifications.It automatically disappears after a few seconds, but can also be dismissed manually.

Where You’ve Seen It:
- “Item added to cart” ,“Message sent” , “Copied to clipboard”

These are Snackbars — they inform the user about something that just happened.

**Alert**

An Alert is a message box used to show important information, warnings, or errors with different colors and icons.It can be used inside a Snackbar or shown alone in the page layout.

Example of Alert Types:

| Alert Type | Purpose                 | Color |
| ---------- | ----------------------- | ----- |
| `success`  | Success or confirmation | Green |
| `error`    | Something went wrong    | Red   |
| `warning`  | Caution needed          | Amber |
| `info`     | Informational           | Blue  |

*Components Involved*

| Component    | Role                                                |
| ------------ | --------------------------------------------------- |
| `Snackbar`   | Wrapper for the popup message box                   |
| `Alert`      | The message content (can be used inside `Snackbar`) |
| `AlertTitle` | Optional — adds a bold title to the alert           |

**Snackbar Props**

| Prop               | Type     | Description                                    |
| ------------------ | -------- | ---------------------------------------------- |
| `open`             | boolean  | Controls if it’s visible                       |
| `onClose`          | function | Called when it closes (after timeout or click) |
| `autoHideDuration` | number   | Time in ms before auto-dismiss                 |
| `message`          | string   | Text shown in the snackbar (basic usage)       |
| `anchorOrigin`     | object   | Controls where the snackbar appears            |
| `action`           | node     | Optional buttons inside (like “Undo”)          |


anchorOrigin Format

```
anchorOrigin={{
  vertical: 'top' | 'bottom',
  horizontal: 'left' | 'center' | 'right'
}}

```
```
anchorOrigin={{ vertical: 'bottom', horizontal: 'center' }}
```

**Alert Props**

| Prop       | Type      | Description                           |
| ---------- | --------- | ------------------------------------- |
| `severity` | string    | `error`, `warning`, `info`, `success` |
| `variant`  | string    | `standard`, `filled`, `outlined`      |
| `onClose`  | function  | Closes the alert if dismissible       |
| `icon`     | ReactNode | Custom icon (optional)                |

*Example full:*

```
import React, { useState } from 'react';
import {
  Snackbar,
  Alert,
  AlertTitle,
  Button,
  Stack
} from '@mui/material';

export default function SnackbarAlertExample() {
  const [open, setOpen] = useState(false);

  const handleClick = () => setOpen(true);
  const handleClose = (event, reason) => {
    if (reason === 'clickaway') return;
    setOpen(false);
  };

  return (
    <Stack spacing={2}>
      <Button variant="contained" onClick={handleClick}>
        Show Success Message
      </Button>

      <Snackbar
        open={open}
        autoHideDuration={4000}
        onClose={handleClose}
        anchorOrigin={{ vertical: 'bottom', horizontal: 'center' }}
      >
        <Alert severity="success" variant="filled" onClose={handleClose}>
          <AlertTitle>Success</AlertTitle>
          You have successfully completed the action!
        </Alert>
      </Snackbar>
    </Stack>
  );
}
```

####  Progress Indicators (Circular & Linear)

**Progress** Indicators visually show that something is loading, processing, or ongoing.

Two Types in Material UI

| Type               | Description                               | Example Use Case               |
| ------------------ | ----------------------------------------- | ------------------------------ |
| `LinearProgress`   | A horizontal bar that fills left to right | File upload, page load         |
| `CircularProgress` | A spinning circle                         | Loading spinner, waiting state |


**CircularProgress**

A circular spinner that rotates continuously or fills like a pie chart (depending on mode).

```
import CircularProgress from '@mui/material/CircularProgress';

```

**Main Props for circular progress**

| Prop        | Type   | Description                                  |
| ----------- | ------ | -------------------------------------------- |
| `color`     | string | `"primary"`, `"secondary"`, `"inherit"`      |
| `size`      | number | Diameter in pixels (e.g., `40`, `60`, etc.)  |
| `thickness` | number | How bold the stroke is (default: `3.6`)      |
| `variant`   | string | `"indeterminate"` (default), `"determinate"` |
| `value`     | number | From `0` to `100` — used only in determinate |

**LinearProgress**
A horizontal bar that fills from left to right, either endlessly or based on a progress value.

```
import LinearProgress from '@mui/material/LinearProgress';
```

*Main Props*

| Prop      | Type   | Description                                  |
| --------- | ------ | -------------------------------------------- |
| `variant` | string | `"indeterminate"` or `"determinate"`         |
| `value`   | number | From `0` to `100` (used in `determinate`)    |
| `color`   | string | `"primary"`, `"secondary"`, `"success"` etc. |
| `sx`      | object | Styling (e.g., width, margin, background)    |


| Type          | Behavior                                        |
| ------------- | ----------------------------------------------- |
| Indeterminate | Spinner or bar keeps looping (unknown duration) |
| Determinate   | Fills up based on a value (known percentage)    |

**when to use what**

| Scenario                       | Use                      |
| ------------------------------ | ------------------------ |
| App is waiting on data load    | Circular (indeterminate) |
| Uploading a file (know % done) | Linear (determinate)     |
| Showing background task        | Circular (small, corner) |


Example Code:

```
import React, { useState, useEffect } from 'react';
import {
  Box,
  CircularProgress,
  LinearProgress,
  Typography,
  Button,
  Stack
} from '@mui/material';

export default function ProgressExample() {
  const [progress, setProgress] = useState(0);
  const [loading, setLoading] = useState(false);

  const handleStart = () => {
    setLoading(true);
    setProgress(0);
  };

  useEffect(() => {
    if (!loading) return;

    const timer = setInterval(() => {
      setProgress((prev) => {
        if (prev >= 100) {
          setLoading(false);
          clearInterval(timer);
          return 100;
        }
        return prev + 10;
      });
    }, 500);

    return () => clearInterval(timer);
  }, [loading]);

  return (
    <Box sx={{ width: '100%', textAlign: 'center', mt: 4 }}>
      <Stack spacing={2} alignItems="center">
        <Button variant="contained" onClick={handleStart}>
          Start Task
        </Button>

        {loading ? (
          <>
            <CircularProgress color="primary" />
            <LinearProgress
              variant="determinate"
              value={progress}
              sx={{ width: '60%' }}
            />
            <Typography variant="body2">{progress}% completed</Typography>
          </>
        ) : (
          <Typography variant="h6" color="success.main">
            Task complete!
          </Typography>
        )}
      </Stack>
    </Box>
  );
}
```

##### Backdrop and Skeleton Loaders

A **Backdrop** is a semi-transparent screen that covers your app and visually blocks interaction.
It’s usually shown when the app is loading or waiting for a task to complete.

When to Use a Backdrop

| Situation                       | Why Use Backdrop                               |
| ------------------------------- | ---------------------------------------------- |
| Submitting a form               | Show something is in progress and block clicks |
| Loading dashboard data          | Prevent UI interaction until it's ready        |
| Performing sensitive operations | Prevent double-submits or errors               |

**Props for <Backdrop>**

| Prop       | Type       | Description                                          |
| ---------- | ---------- | ---------------------------------------------------- |
| `open`     | `boolean`  | Controls visibility                                  |
| `onClick`  | `function` | Optional — called when user clicks the backdrop      |
| `sx`       | `object`   | Custom inline styles (e.g., color, zIndex, blur)     |
| `children` | `node`     | Optional — you can place a spinner or message inside |

*Common Pair*: Backdrop + CircularProgress
You’ll often combine Backdrop + CircularProgress to show a centered loading spinner.

Example:

```
import React, { useState } from 'react';
import { Backdrop, CircularProgress, Button } from '@mui/material';

export default function BackdropExample() {
  const [open, setOpen] = useState(false);

  const handleToggle = () => setOpen(!open);

  return (
    <>
      <Button onClick={handleToggle} variant="contained">
        {open ? 'Hide' : 'Show'} Backdrop
      </Button>

      <Backdrop
        open={open}
        sx={{ color: '#fff', zIndex: (theme) => theme.zIndex.drawer + 1 }}
      >
        <CircularProgress color="inherit" />
      </Backdrop>
    </>
  );
}
```

#### What is a Skeleton

A Skeleton Loader shows a gray placeholder (like an empty box or line) that mimics the shape of the content while it's loading.

It improves perceived performance by showing the user something is loading — instead of just an empty white screen.

 *Props for <Skeleton>*

 | Prop        | Type             | Description                               |
| ----------- | ---------------- | ----------------------------------------- |
| `variant`   | string           | `'text'`, `'rectangular'`, `'circular'`   |
| `width`     | number or string | Width of the skeleton                     |
| `height`    | number or string | Height of the skeleton                    |
| `animation` | string           | `'pulse'` (default), `'wave'`, or `false` |
| `sx`        | object           | Style overrides (margin, radius, etc.)    |

**Skeleton Variants**

| Variant       | What it looks like             |
| ------------- | ------------------------------ |
| `text`        | Gray line (like a text line)   |
| `rectangular` | Gray block (like a card/image) |
| `circular`    | Gray circle (like avatar)      |

Example code:

```
import React, { useState, useEffect } from 'react';
import { Skeleton, Card, CardContent, Typography } from '@mui/material';

export default function SkeletonExample() {
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    // Simulate API load
    const timer = setTimeout(() => setLoading(false), 3000);
    return () => clearTimeout(timer);
  }, []);

  return (
    <Card sx={{ width: 300, m: 2 }}>
      <CardContent>
        {loading ? (
          <>
            <Skeleton variant="text" width="80%" />
            <Skeleton variant="text" width="60%" />
            <Skeleton variant="rectangular" width="100%" height={100} sx={{ mt: 2 }} />
          </>
        ) : (
          <>
            <Typography variant="h6">Hello, John!</Typography>
            <Typography variant="body2">Here is your profile info.</Typography>
            <img
              src="https://via.placeholder.com/300x100"
              alt="Loaded"
              style={{ width: '100%', marginTop: 16 }}
            />
          </>
        )}
      </CardContent>
    </Card>
  );
}
```

#### Tooltip and Popover

**Tooltip**

Tooltip is a small floating label that appears when the user hovers, focuses, or touches an element.

*when to use a tooltip*

| Use Case                          | Example                                  |
| --------------------------------- | ---------------------------------------- |
| Explain icon functions            | "What does this button do?"              |
| Provide shortcut keys             | “Copy (Ctrl + C)”                        |
| Describe UI labels in more detail | “This setting affects global visibility” |

Tooltip Props

| Prop                   | Type        | Description                                   |
| ---------------------- | ----------- | --------------------------------------------- |
| `title`                | string/node | The content inside the tooltip (required)     |
| `placement`            | string      | Where the tooltip appears (top, bottom, etc.) |
| `arrow`                | boolean     | Adds a pointing arrow                         |
| `enterDelay`           | number      | Delay before showing (ms)                     |
| `leaveDelay`           | number      | Delay before hiding (ms)                      |
| `followCursor`         | boolean     | Tooltip follows the mouse                     |
| `disableHoverListener` | boolean     | Prevent hover triggering                      |

**Placement oprtions:**

| Placement Value                                          | Tooltip Position  |
| -------------------------------------------------------- | ----------------- |
| `"top"`                                                  | Above the element |
| `"bottom"`                                               | Below the element |
| `"left"`                                                 | To the left       |
| `"right"`                                                | To the right      |
| Variants like `"top-start"` or `"bottom-end"` also exist |                   |

exmple:

```
import React from 'react';
import { Tooltip, IconButton } from '@mui/material';
import InfoIcon from '@mui/icons-material/Info';

export default function TooltipExample() {
  return (
    <Tooltip title="More info about this setting" placement="right" arrow>
      <IconButton>
        <InfoIcon />
      </IconButton>
    </Tooltip>
  );
}
```

**Popover**

A Popover is a larger floating panel anchored to a specific element, triggered by a click or focus.
It can contain rich content like buttons, text, inputs, etc.

*when to use a Popover*

| Use Case                         | Example                             |
| -------------------------------- | ----------------------------------- |
| Show extra options               | "More Actions" menu on button click |
| Display related content          | Profile preview on username click   |
| Inline editing or dropdown logic | Click-to-edit panels                |

**Popover Props**

| Prop              | Type        | Description                                         |
| ----------------- | ----------- | --------------------------------------------------- |
| `open`            | boolean     | Whether the popover is visible                      |
| `anchorEl`        | HTMLElement | The element it should attach to (click target)      |
| `onClose`         | function    | Callback to close the popover                       |
| `anchorOrigin`    | object      | Controls where it appears in relation to the anchor |
| `transformOrigin` | object      | Adjusts the popover's internal alignment            |
| `children`        | node        | The content shown inside the popover                |

Example code:

```
import React, { useState } from 'react';
import {
  Popover,
  Typography,
  Button,
  Box
} from '@mui/material';

export default function PopoverExample() {
  const [anchorEl, setAnchorEl] = useState(null);

  const handleClick = (event) => {
    setAnchorEl(event.currentTarget); // Save clicked button
  };

  const handleClose = () => {
    setAnchorEl(null);
  };

  const open = Boolean(anchorEl);

  return (
    <>
      <Button variant="contained" onClick={handleClick}>
        Show Popover
      </Button>

      <Popover
        open={open}
        anchorEl={anchorEl}
        onClose={handleClose}
        anchorOrigin={{
          vertical: 'bottom',
          horizontal: 'center'
        }}
        transformOrigin={{
          vertical: 'top',
          horizontal: 'center'
        }}
      >
        <Box sx={{ p: 2 }}>
          <Typography>This is a popover message.</Typography>
        </Box>
      </Popover>
    </>
  );
}
```

# Data Display Components

**Avatar and Badge**

*What is an avatar?*

An Avatar is a small circular or square image that represents a person or object, often used in UIs to show a profile picture or user initials.

*Key Props of Avatar*

| Prop       | Type   | Purpose                                            |
| ---------- | ------ | -------------------------------------------------- |
| `alt`      | string | Text used when image fails to load                 |
| `src`      | string | Image URL to show in the avatar                    |
| `sx`       | object | System props for styling like size, border, etc.   |
| `children` | node   | You can put text/initials inside (when no image)   |
| `variant`  | string | `'circular'` (default), `'rounded'`, or `'square'` |

Initials as Avatar

```
<Avatar>JM</Avatar>
```
Image Avatar

```
<Avatar src="https://i.pravatar.cc/150" alt="John Kim" />
```
on props 

```
<Avatar variant="square">A</Avatar>
<Avatar variant="rounded">B</Avatar>
```

**What Is a Badge?**

A Badge is a small dot, number, or symbol that appears next to another component (like an icon or avatar) to show a notification, count, or status.

| Real Use Case         | MUI Badge Equivalent            |
| --------------------- | ------------------------------- |
| WhatsApp unread chats | A red dot with number on avatar |
| Gmail new messages    | Count badge on inbox icon       |
| Status indicator      | Green dot on profile avatar     |

**Key Props in Badge**

| Prop           | Type   | What It Does                                     |
| -------------- | ------ | ------------------------------------------------ |
| `badgeContent` | node   | What to show inside the badge (number, letter)   |
| `color`        | string | Badge color: `'primary'`, `'error'`, `'success'` |
| `overlap`      | string | `'rectangular'` or `'circular'` for positioning  |
| `anchorOrigin` | object | Controls vertical/horizontal position            |
| `variant`      | string | `'dot'` or `'standard'`                          |
| `sx`           | object | Custom styling                                   |

*Example:*

```
import React from 'react';
import { Avatar, Badge, Stack, Typography } from '@mui/material';

export default function AvatarBadgeDemo() {
  return (
    <Stack spacing={3} alignItems="center">
      <Typography variant="h6">Avatar with Image</Typography>
      <Avatar src="https://i.pravatar.cc/100" />

      <Typography variant="h6">Avatar with Initials</Typography>
      <Avatar sx={{ bgcolor: 'primary.main' }}>JK</Avatar>

      <Typography variant="h6">Avatar with Notification Badge</Typography>
      <Badge badgeContent={3} color="error">
        <Avatar src="https://i.pravatar.cc/100" />
      </Badge>
    </Stack>
  );
}
```