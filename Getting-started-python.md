# Getting-started-python

## 1. Setup

* Make sure you have [VSCode](https://code.visualstudio.com/download) Version 1.93.0 or later installed
* Open your python project 
* Run the following command on the VSCode terminal:

```
pip install -r requirements.txt
```

* Make sure you have pytest install

```
pip install pytest
```
<br>


## 2. Browse the extension

* Click on Early's Extension icon on the left bar
* View the files and method tree on the project tree

<figure>
    <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/python-extension.png"
         alt="build the project" width=400 >
</figure>
<br>


## 3. Using the Extension

**Navigate through the extension views** 

 <span>1. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/Icon-testablecode.png" width=100 />  <span>  A tree of all the testable methods /functions in the project</span>


<span>2. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/generate-test-icon.png" width=20 />  <span>   Play (our magic wand) button next to method names will generate test
 </span>

<span>3. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/icon-gototests.png" width=20 />  <span>  "Go-to tests" go to the unit tests file that was generated </span>

<span>4. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/Icon-codelens.png" width=200 />  <span>  code lens above method/function names </span>

<br>

![extension](https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/extension-overview-python.png)
<br>


## 4. Generating Your First Tests

There are two ways to generate unit tests

<span>1. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/generate-test-icon.png" width=20 />  <span>  Play (our magic wand) button via the code explorer, next to the method/function name.  
 </span>

<span>2. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/icon-codelens-gentest.png" width=140 />  <span>  "Early AI: Generate tests" Code lens above each method/function name on the code editor.  
 </span>

 </span>
Once you generate a test a VSCode notification bar will pop up on the bottom right corner until the generation is completed. Test generation can take between 15 to 30 seconds depending on the complexity of the code base and API response time.
<br>

![GeneratingTests](https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/generating-tests.png)
<br> 


## 5. Review the Generated Tests 

**Now you are ready to view the tests generated**

EarlyAI generates complex tests that includes mocks, logic, happy path and edge cases. We also  generate “Green” and “Red” unit tests.

* <span style="color: green;">Green</span> are healthy passing unit tests
* <span style="color: red;">Red</span> could be **good** tests that are revealing a bug or erroneous unit tests.

You can go-to the generated tests and view them in two ways.

<span>1. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/icon-gototests.png" width=20 />  <span>  "Go-to tests" go to tests button next to the method name </span>


<span>2. </span> <img src="https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/icon-codelens-gototests.png" width=140 />  <span>  "Early AI: go to tests" Code lens above each public method/function name on the code editor.  
 </span>

<br>

![ViewTests](https://raw.githubusercontent.com/earlyai/earlyai-docs/main/media/view-tests.png)
<br>


## 6. Pytest.ini

**Basic configuration for pytests**

```
[pytest]

testpaths = main-tests-folder

python_files = test_early_* or spec_early_*

markers =
    happy_path: mark a test as a happy path test
    edge_case: mark a test as an edge case test

norecursedirs = 
    .git 
    __pycache__ 
    node_modules 
    venv 
    .venv
```
