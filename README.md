# glycopeptide-multi-result

> Wrapper over glycoheatmap, this element is used by simple and advanced search elements. 
> When query gets submitted parent element assigns to it json file containing list of query masses. 
> This event triggers generation of navigation tabs on side of the internal heatmap element.
> After each server response, the json is updated with data and the corrsponding tab is being enabled.
> By selecting tab data are passed to the heatmap element. 

## Usage

1. Import polyfill:

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents-lite.min.js"></script>
    ```

2. Import custom element:

    ```html
    <link rel="import" href="bower_components/glycopeptide-simple-search/glycopeptide-multi-result.html">
    ```

3. Start using it!

    ```html
    <glycopeptide-multi-result></glycopeptide-multi-result>
    ```

## Options

Attribute     | Options     | Default      | Description
---           | ---         | ---          | ---
`masses`      | *array*     |  null        | list of masses passed from the search form,
              |             |              | change triggers generation of navigation tabs
`datasets`    | *array*     | `{}`         | container for charts data
`selected`    | *number*    |  null        | index of currently selected tab 

## Methods

Method        | Parameters   | Returns     | Description
---           | ---          | ---         | ---
`newDataset()`| None.        | Nothing.    | Function used to update this.datasets property, search forms
              |              |             | are querying the server separately for each mass and subsequently
              |              |             | use this function to pass the received dataset
`_datasetSected()`| None.    | Nothing.    | Listener monitoring which tab is currently selected and triggering 
              |              |             | update of the chart data 

## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

1. Install [bower](http://bower.io/) & [polyserve](https://npmjs.com/polyserve):

    ```sh
    $ npm install -g bower polyserve
    ```

2. Install local dependencies:

    ```sh
    $ bower install
    ```

3. Start development server and open `http://localhost:8080/components/glycopeptide-multi-result/`.

    ```sh
    $ polyserve
    ```

## History

For detailed changelog, check [Releases](https://bitbucket.org/sib-pig/glycopeptide-multi-result/releases).

## License

[MIT License](http://opensource.org/licenses/MIT)
