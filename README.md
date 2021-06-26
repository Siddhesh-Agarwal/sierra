# sierra

![sierra logo](https://github.com/BrainStormYourWayIn/sierra/blob/main/logo.jpg)

Sierra is a Python3 library for building and integrating web applications with HTML and CSS using simple enough syntax. You can develop your web applications purely with Python, taking advantage of its functionalities and integrating them to the fullest.  

### Sierra makes integration with Flask much easier and faster! See the examples below



[![Downloads](https://pepy.tech/badge/sierra)](https://pepy.tech/project/sierra)    [![Downloads](https://pepy.tech/badge/sierra/month)](https://pepy.tech/project/sierra)

### v1.2.3 is out  
Use `pip install --upgrade sierra` to upgrade

________________________________

## Documentation

Check out the [Official documentation of Sierra](https://brainstormyourwayin.github.io/sierra.github.io/)

Check out a [comprehensive example](https://github.com/BrainStormYourWayIn/sierra_doc/blob/main/doc.py) of its use

________________________________

## Sierra

```python
from sierra import *

title('This is how you enter the title of your web application')
head('I love Sierra!', type='h1', color='rgb(31, 48, 92)')
openBody(background_color='green', opacity=0.8)

a = tTags(div_class='newClass')
b = tTags(p=True)
a.start_div()
b.css(font_family='Times New Roman', color='purple')
b.start_p('This is a paragraph under div "newClass!" CSS can be added with .css!', close=True)
closeTags('div')

abc = 'stuff!'
c = ['This', 'is', 'easy', abc]

addBullets(points=c, ul=False, type='i')

openTags('XMLTag')
b.start_p('This is an  XML tag', True)
writeCSS('XMLTag', {"font-size": "15px", "background-color": "rgb(240, 237, 228)"})
b.start_p('You can enter custom CSS styling arguments like this, or use cTags() to make it easy!', True)
closeTags('XMLTag')

autoPrettify()                # Closes unclosed tags automatically and improves overall look of the code
```
Outputs in index.html and style.css:

    <!DOCTYPE html>
    <html lang="en">
     <meta charset="utf-8"/>
     <head>
      <title> This is how you enter the title of your web application </title>
      <link href="style.css" rel="stylesheet"/>
      <h1>I love Sierra!</h1>
     </head>
     <body>
      <div class="newClass">
       <p>
        This is a paragraph under div "newClass!" CSS can be added with .css!
       </p>
      </div>
      <ol start="1" type="i">
       <li>This</li>
       <li>is</li>
       <li>easy</li>
       <li>stuff!</li>
      </ol>
      <xmltag>
       <p>
        This is an  XML tag
       </p>
       <p>
        You can enter custom CSS styling arguments like this, or use cTags() to make it easy!
       </p>
      </xmltag>
     </body>
    </html>

```

h1 {
    color: rgb(31, 48, 92);
    font-family: Arial;
    text-align: left;
}

body {
    background: False;
    background-color: green;
    background-image: False;
    opacity: 0.8;
    background-size: cover;
    background-attachment: fixed;
}

p {
    color: purple;
    font-family: Times New Roman;
    display: block;
}

XMLTag {
	font-size: 15px;
	background-color: rgb(240, 237, 228);
}
```

Using this with Flask makes life easier

```python
from flask import Flask, render_template
from sierra import *

app = Flask(__name__)

def the_template():
    title('bulleted_and_description_lists')
    head('this is a bulleted list')
    
def bulleted_list():
    the_template()
    abc = 'stuff!'
    bullets = ['This', 'is', 'easy', abc]
    addBullets(points=bullets)
    autoPrettify()

def description_list():
    the_template()
    a = [['coffee'], ['black coffee', 'black tea']]
    def_lists(a)
    autoPrettify()

@app.route("/bulleted_list")
def show_bulleted_list():
    return bulleted_list()
    return render_template('index1.html')
    

@app.route("/description_list")
def show_description_list():
    return description_list()
    return render_template('index2.html')
    
if __name__ == '__main__':
    app.run()

```
Of course, you can also define the functions in separate files and import it  

The directory structure needs to be sorted out first before running this. Run the code in `templates/`. In Sierra, the HTML and CSS files are automatically named `index.html` and `style.css` in the working directory, which will be sorted in the next release. 

________________________________

## Installation

### Method 1: pip install

type the below command in terminal:

`pip install sierra`

### Method 2: Download ZIP file

**To download the zip file:** click on the `download` button and then click on the `Download ZIP` button. The zip file will get downloaded in the downloads folder.

**To unzip the zip file:** open the zipped folder and select `Extract All`. Development can be done in `sierra-main/sierra` and not in `sierra-main/src/sierra`
Check out [doc.py](https://github.com/BrainStormYourWayIn/sierra_doc/blob/main/doc.py) for a better view on how to start off

### Method 3: Clone repository

To clone the repository, type:

`gh repo clone BrainStormYourWayIn/sierra`
or
`git clone https://github.com/BrainStormYourWayIn/sierra.git`

in your terminal/shell.

________________________________


Use `pip install --upgrade sierra` to upgrade the library

________________________________


## See the [official documentation of Sierra](https://brainstormyourwayin.github.io/sierra.github.io/) for more!

________________________________

## Upcoming

- Integration with Flask (directory structure, automatic support with smaller funcs etc)
- More efficient way to close tags (apart from autoPrettify())

________________________________

## License

   Copyright 2021 BrainStormYourWayIn

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

> Pandas (pandas)
>> Copyright (c) 2008-2011, AQR Capital Management, LLC, Lambda Foundry, Inc. and PyData Development Team   
>> Copyright (c) 2011-2020, Open source contributors.
