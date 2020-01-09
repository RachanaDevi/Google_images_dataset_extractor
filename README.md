# Google_images_dataset_extractor
Code for extracting google images https://www.pyimagesearch.com/2017/12/04/how-to-create-a-deep-learning-dataset-using-google-images/

### Open Inspect element
### Scroll down till relevant images
### Copy code in console

// pull down jquery into the JavaScript console <br/>
var script = document.createElement('script');
script.src = "https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(script);

// grab the URLs <br/>
var urls = $('.rg_di .rg_meta').map(function() { return JSON.parse($(this).text()).ou; });

// write the URls to file (one per line) <br/>
var textToSave = urls.toArray().join('\n');
var hiddenElement = document.createElement('a');
hiddenElement.href = 'data:attachment/text,' + encodeURI(textToSave);
hiddenElement.target = '_blank';
hiddenElement.download = 'urls.txt';
hiddenElement.click();



### Run google_images_extraction.py
#### images/food_tem directory  should already be created
python google_images_extraction.py --urls urls.txt --output images/food_item
