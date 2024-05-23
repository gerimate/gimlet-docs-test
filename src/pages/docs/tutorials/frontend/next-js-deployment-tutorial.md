# Next.js Deployment Tutorial

Next.js is a React framework made by Vercel. It's one of the most popular frameworks for frontend applications. You can deploy it with Gimlet as documented below.

## Step 1: Getting Started with Gimlet

Log in to Gimlet by connecting your GitHub or GitLab. The repositories available to you will be listed after successful connection.

If you can't find the repository having your Next.js application, you can use the search bar to find it.

Click the Import button next to it to add it to Gimlet, and click the I am done importing button to save the added repo. You can import multiple repositories.

## Step 2: Deployment of a Next.js Application

Navigate to deployment settings by clicking the card of the repository.

You can deploy the Next.js frontend as a Web Application Template, and you'll need to select the Dockerfile container image option.

Select the GitHub Container Registry option in the Registry section.

Make sure that your `next.config.js` file has `output: 'export'` set.

## Step 3: Check out Your Next.js Frontend

After container status turning to running, a clickable link will appear under the Address section of status. You can open that in your browser to check out the Next.js application.

Click `Add deployment configuration`.

![Screenshot with add deployment configuration button](/next-js-tutorial-02.png)

Select the static site template and specify the repo’s URL.

![Screenshot with template selection and config settings](/next-js-tutorial-03.png)

Navigate to Build settings, where `Built assets` should be `/out`, and make sure that your `next.config.js` file has `output: 'export'` set.

![Screenshot with build settings](/next-js-tutorial-04.png)

Click save.

## Step 3: Deploy

After saving configuration, Gimlet will open a pull request in the repository of the Next.js app. Merge the pull request.

![Screenshot of GitHub pull request](/next-js-tutorial-05.png)

Click deploy in Gimlet and watch the status. After a while, status should become `running` and your Next.js app should be deployed successfully.

![Screenshot of status page](/next-js-tutorial-06.png)

## Step 4: Port-Forwarding

Your app still won’t be accessible from the internet. To make it accessible, follow the steps below.

Right to the app’s address, there is a `Port-forward command` button. Click the button to generate a command.

Run the command in the terminal. Here’s an example:

```

// deploy is an example namespace

// nextjs-app is the example app’s name

kubectl port-forward deploy/nextjs-app 10081:80

```

If you enter the address mentioned above in your browser, and type `:10081` at the end, you should be able to access your Next.js application.

## Use Cases

Here are a few examples of why hosting your Next.js application with Gimlet is for you:

- **OAuth & HTTPS/SSL:** Add social authentication and secure your Next.js application.
- **Branch previews:** Test changes on real environments.
- **Advanced deployment capabilities:** Rollbacks and automated deployments.

## Try Now

> Try Gimlet now with your Next.js application for free [here]().
