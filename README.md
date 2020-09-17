# Kentico Kontent Hugo article sample
Sample [Hugo static site generator](https://gohugo.io/) project using the [Kentico Kontent Delivery JavaScript SDK](https://github.com/Kentico/kontent-delivery-sdk-js) to retrieve content.

This application is meant for use with the Dancing Goat sample project within Kentico Kontent. If you don't have your own Sample Project, any administrator of a Kentico Kontent subscription [can generate one](https://app.kontent.ai/sample-project-generator).

## Application setup

### Running the application
To run the app:
1. Clone the app repository with your favorite GIT client
1. Open the solution in Visual Studio Code or your favorite IDE
1. Update the Kontent project ID in `cms-scripts\config.js` (detailed instructions available below)
1. From the terminal run:
   1. `npm install`
   1. `npm run build`
   1. `npm start`
   
Running `npm run build` creates markdown copies of the Dancing Goat sample articles in the `content/articles` directory.
Running `npm start` starts the Hugo server on `http://localhost:1313` and a webhook endpoint at `http://localhost:3000` . Information regarding webhooks can be seen in the "Setting up webhooks" section below.

Alternatively, you can run `npm run build && hugo serve` in the terminal to run just the Hugo site without the webhook functionality.

### Connecting to your sample project
If you already have a [Kentico Kontent account](https://app.kontent.ai), you can connect this application to your version of the Sample project.

1. In Kentico Kontent, choose Project settings from the app menu
1. Under Development, choose API keys and copy the Project ID
1. Open the `cms-scripts\config.js` file
1. Use the values from your Kentico Kontent project in the Delivery Client initialization:

```javascript
const KenticoContent = require('@kentico/kontent-delivery');

const deliveryClient = new KenticoContent.DeliveryClient({
    projectId: '<your_project_id>',
});

exports.deliveryClient = deliveryClient;
```
1. Save the changes
1. Run the application from the terminal

## Setting up webhooks
> under construction.

## Adding a Theme
> under construction.

## Content administration
1. Navigate to <https://app.kontent.ai> in your browser.
1. Sign in with your credentials.
1. Manage content in the content administration interface of your sample project.

You can learn more about content editing with Kentico Kontent in our [Documentation](https://docs.kontent.ai/).

