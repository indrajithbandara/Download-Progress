# Page-Loading
A small, low-level library to create awesome page loading and download progress bars.

Page Loading as its name states was originally made to create a progress bar for page loading but you can use it to create progress bars for any type of file downloads. 

### How to start?

* Install using npm `npm install page-loading`
* If using ECMAScript 6 then `import PageLoading from 'page-loading'` then `new PageLoading(filesToLoad)`
* If using ECMAScript 5 then include `<script src="~/node_modules/dist/page-loading.js"></script>` in the head of your index.html then `PageLoading(filesToLoad)`

### How to use?

    var files = ['myJS.js','myCSS.css','myText.txt'];
    var pl = PageLoading(files);
    pl.on('progress',function(e){
        console.log(e.detail + ' combined percentage loaded!');
    }).on('afterLoading',function(e){
        console.log(e.detail.url + ' is completely loaded!');
        console.log(e.detail.response); //this is the content of the loaded file
    });
    pl.init();
    
### Methods
* **on**: Attaches a callback to one of the events
* **init**: Initializes the loading process
    
### Events

* **beforeLoading**: Dispatches right before the loading process starts
* **afterLoading**: Dispatches once after each url is completely loaded
* **progress**: Dispatches when the progress value (the percentage) changes

#### Feel free to contribute, leave suggestion or issues. 

## License

This project is licensed under the [MIT License](https://raw.githubusercontent.com/Amin52J/Page-Loading/master/LICENSE).