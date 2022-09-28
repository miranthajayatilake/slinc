

## Usage

### Updating configuration

The project can be configured via a JSON [config file](src/config/engine.json).

**NOTE** - This project needs a hosted elastic search cluster with indexed documents. 

- [Elastic](https://github.com/elastic) will provide more information on how to do this. You can use their hosted solution as well. 
- The documents indexed were taken from Andrej Karpathy's [Lexicap](https://karpathy.ai/lexicap/)

**More documentation will be done on this shortly..**

## Instructions

You can easily control things like...

- The Engine the UI runs against
- Which fields are displayed
- The filters that are used

If you would like to make configuration changes, there is no need to regenerate
this app from your App Search Dashboard!

You can simply open up the
[engine.json](src/config/engine.json) file, update the [options](#config),
and then restart this app.



### Configuration options <a id="config"></a>

The following is a complete list of options available for configuration in [engine.json](src/config/engine.json).

| option               | value type    | required/optional | source                                                                                                                                                                                          |
| -------------------- | ------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `engineName`         | String        | required          | Found in your App Search Dashboard.                                                                                                                                                             |
| `endpointBase`       | String        | required*         | (*) Elastic Enterprise Search deployment URL, example: "http://127.0.0.1:3002". Not required if using App Search on swiftype.com.                                                               |
| `hostIdentifier`     | String        | required*         | (*) Only required if using App Search on swiftype.com.                                                                                                                                          |
| `searchKey`          | String        | required          | Found in your App Search Dashboard.                                                                                                                                                             |
| `searchFields`       | Array[String] | required          | A list of fields that will be searched with your search term.                                                                                                                                   |
| `resultFields`       | Array[String] | required          | A list of fields that will be displayed within your results.                                                                                                                                    |
| `querySuggestFields` | Array[String] | optional          | A list of fields that will be searched and displayed as query suggestions.                                                                                                                      |
| `titleField`         | String        | optional          | The field to display as the title in results.                                                                                                                                                   |
| `urlField`           | String        | optional          | A field with a url to use as a link in results.                                                                                                                                                 |
| `sortFields`         | Array[String] | optional          | A list of fields that will be used for sort options.                                                                                                                                            |
| `facets`             | Array[String] | optional          | A list of fields that will be available as "facet" filters. Read more about facets within the [App Search documentation](https://www.elastic.co/guide/en/app-search/current/facets-guide.html). |

### External configuration

If you are embedding this app inside of another page, and you would like to
source the configuration from outside of the `engine.json` file,
you can simply write the configuration directly to `window.appConfig`.

### If you are checking this project out directly from GitHub... <a id="github"></a>

You can follow the previous steps, but then you will need to configure
[engine.json](src/config/engine.json).

To do so, make a copy of [engine.json.example](src/config/engine.json.example),
rename it to `engine.json` and configure it with your Engine's specific details.

```bash
cp src/config/engine.json.example src/config/engine.json
```

```
# Run this to set everything up
npm install

# Run this to start your application and open it up in a new browser window
npm start
```

## Deploy and Share

This app can be easily published to any server as static assets and served. We recommend [Netlify](https://www.netlify.com/), but you have other [options](https://facebook.github.io/create-react-app/docs/deployment) as well.

To deploy:

```
npm run build
npm install netlify-cli -g
netlify deploy # enter ./build as the deploy path
```

You'll then simply follow the command prompt to log into Netlify and deploy your site. This can be completed in just a few minutes.

## Customization

This project is built with [Search UI](https://github.com/elastic/search-ui), which is a React library for building search experiences. If you're interested in using this project as a base for your own, most of
what you'll need can be found in the Search UI documentation.

## License 📗

[Apache-2.0](https://github.com/elastic/app-search-reference-ui-react/blob/master/LICENSE.md) © [Elastic](https://github.com/elastic)
