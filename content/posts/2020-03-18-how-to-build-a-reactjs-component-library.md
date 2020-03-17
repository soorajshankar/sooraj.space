---
template: post
title: How to build a ReactJS component library?
slug: building-a-react-library
draft: true
date: 2020-03-07T06:09:37.175Z
description: >-
  A brief guide on creating a react component library, a style guide or even a
  design system.
category: reactjs
tags:
  - reactjs library storybook styled-components
---
A brief guide on creating a react component library, a style guide or even a design system.

## Step 1

Components should be reusable and configurable with most of its internal features and UI.

1. simply create-react-app.
   ```
   npx create-react-app fresh-designs
   ```
2. open the project on your text editor or IDE
3. create a file `src/components/Button/index.jsx ` 
   ```
   import React from 'react'const Button =({text,onClick})=><button >{text}</button>export default Button; 
   ```



## Step 2 Storybook

Documentation and visualisation is very important. I found there is a popular tool for that [StoryBookJS](https://storybook.js.org/)

Storybook is a library where you can develop UI components in a isolated manner, there are lot of addons available to try and test componets dynamically. and its really cool!

We will be following automatic storybook setup as mentioned [here](https://storybook.js.org/docs/guides/guide-react/).

1. Just run the below command, storybook will do the all the configuration for you.
   ```
   npx -p @storybook/cli sb init --type react_scripts
   ```
   Storybook configuration with a sample story will be created automatically by the above script.
2. Now run the storybook server
   ```
   yarn storybook// or npm run storybook
   ```
3. Open your browser [`http://localhost:9009`](http://localhost:9009) You will see the storybook running on your browser.
4. Creating Stories: create a file `src/components/Button/button.stories.jsx`
   1. ```
      import React from 'react'import {Button} from './index'export default {  title: 'Button',  component: Button,}export const SubmitButton = () => (  <Button onClick={() => console.log('clicked')} text="Submit" />)
      ```
5. You will start seeing the component loaded on storybook even without restarting storybook.


I wonder how smoothly modern styled components render beautiful UI screens, I should definitley use a styled component.



Going forward,

1. Adding \`styled-components\`
2. Need a bundler that makes the library lightweight and shipable.
   We will be using [RollupJS](https://rollupjs.org/) for bundling the package.
