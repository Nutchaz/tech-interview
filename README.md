# Personality Test Project


> Personality Test is a questionnaire designed to determine which type of personality you have, based on the answers you provide. (The calculation is based on assumptions only.)

## Instruction
Develop the website based on the design linked below

[Design](https://www.figma.com/file/sqJhuPKdNlffwHo5bvswvI/Tech-Interview%2C-Personality-Test?type=design&node-id=0-1) (Please Login)

##### *Fork this repository, customize the code to fit your style, and submit your repository to us via email career@globish.co.th and cc to dusadee.s@globish.co.th.*

###### Spec
 
1. Use Vite Vue3 framework 
2. Write with TypeScript
3. Responsive with max width 720px

###### There are three types of personality, and the scoring criteria are as follows:

1. The Gradual Learner: 131 - 180
2. The Enthusiastic: 91 - 130
3. The Hobbyist: 60 - 90



###### Calculation is based on adding the scores of the selected answer from each question.

| Question      | Choice 1      | Choice 2      | Choice 3      |
| ------------- |:-------------:|:-------------:|:-------------:|
| Q1            | 10  | 20 | 30  |
| Q2            | 30  | 10  | 20  |
| Q3            | 30  | 20  | 10  |
| Q4            | 30  | 10  | 20  |
| Q5            | 20  | 10  |30  |
| Q6            | 20  | 10  | 30  |

NOTE: The last question will not be included in the calculation.

---


# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
