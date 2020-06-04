# My React Notes

> This is my random React notes ;)

---

## Table of Contents:

- [NVM](#NVM)
- [NPM](#NPM)
- [NPX](#NPX)
- [What is NPM and Yarn?](#what-is-npm-and-yarn)
- [What is a **Script** and **`react-scripts`** in `create-react-app`?](#what-is-a-script-and-react-scripts-in-create-react-app)

---

## Difference between **NVM**, **NPX** and **NPM**:

### NVM:

Stand for **N**ode **V**ersion **M**anager, and it's a tool to manage and switch between versions of **Node** very easily. But it's also useful to easily install or upgrade the current version of **Node**.

### NPM:

The **npm** stands for **N**ode **P**ackage **M**anager and it is the default package manager for **Node.js**. It is written entirely in **JavaScript**, it was initially released on January 12, 2010. The **npm** manages all the packages and modules for **Node.js** and consists of command–line client **npm**. It gets installed into the system with the **installation of Node.js**. The required packages and modules in the Node project are installed using **npm**. A package contains all the files needed for a module and modules are the JavaScript libraries that can be included in the Node project according to the requirement of the project.
It provides a way for developers to install packages both globally and locally.

**Execute package with npm:**

- **By typing the local path:** You have to write down the local path of your package like below:

  ```
  ./node_modules/.bin/your-package-name
  ```

- **Locally installed:** You have to open the **package.json** file and write down the below scripts:

  ```JSON
  {
      "name": "Your app",
      "versiuon":  "1.0.0",
      "scripts":  {
              "your-package":  "your-package-name"
      }
  }
  ```

**To run package:** After that, you can run your package by running the below command:

```properties
npm run your-package-name
```

### NPX:

The npx stands for **N**ode **P**ackage e**X**ecute and it comes with the npm, when you installed npm **above 5.2.0** version then automatically npx will installed. **It is an npm package runner that can execute any package that you want from the npm registry without even installing that package.** The npx is useful during a single time use package. If you have installed npm below 5.2.0 then npx is not installed in your system. You can check npx is installed or not by running the following command:

```properties
npx -v
```

If npx is not installed you can install that separately by running the below command.

```properties
npm install -g npx
```

**Execute package with npx:**

Sometimes you might want to take a look at a specific package and try out some commands. But you cannot do that without installing the dependencies in your local node_modules folder.
That’s where npx comes in.

- **Directly runnable:** You can execute your package without installation, to do so run the following command.

  ```properties
  npx your-package-name
  ```

**Differences between npm and npx:**

|                                                                   NPM                                                                   |                                                                                    NPX                                                                                    |
| :-------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|      If you wish to run package through npm then you have to specify that package in your `package.json` and installed it locally.      | A package can be executable without installing the package, it is an npm package runner so if any packages that aren’t already installed it will installed automatically. |
| To use `create-react-app` in npm the commands are `npm install create-react-app` then `create-react-app myApp` (Installation required). |              But in npx you can use that without installing like `npx create-react-app myApp`, this command is required in every app’s life cycle only once.              |
|                                               Npm is a tool that use to install packages.                                               |                                                                Npx is a tool that use to execute packages.                                                                |
|                     Packages used by npm are installed globally you have to care about pollution for the long term.                     |                               Packages used by npx are not installed globally so you have to carefree for the pollution for the long term.                                |

---

## What is NPM and Yarn?

**NPM** and **Yarn** are both package managers. **Package Managers is essentially a way to automate the process of installing, upgrading, configuring or removing software.**

We know that **Yarn** was created by Facebook as an alternative to **NPM**. They created **Yarn** to solve the problems they were having while using **NPM** particularly the problems with consistency, security and speed. **Yarn** has the same feature set while operating faster, more securely and most importantly more reliable.

**NPM Version 5.0**: With their newest release if npm 5 many of the shortcomings of NPM were addressed.

- NPM 5 introduced the `package-lock.json` file for better versioning control.

- NPM 5 is now much faster, but Yarn still edges them out in terms of speed.

- Now supports offline installation for previously downloaded packages.

---

## What is a **Script** and **`react-scripts`** in `create-react-app`?

In programming, **a script is basically a list of instructions that dictates to another program what to do.**

React is no exception; it has scripts to do things.
`create-react-app` ships with four main scripts.

In React apps, scripts are located in the `package.json` file. This file has some default scripts, but it’s still possible to edit them.

```JSON
 "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
```

As you can see, a fresh React app comes with four scripts that use the package `react-scripts`.

---
