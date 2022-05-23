# Q-A-generation 

The kaggle notebooks of the code presented here can be found here :- 

    https://www.kaggle.com/code/swaralipibose/inference-of-squad-model 
    
    https://www.kaggle.com/code/swaralipibose/creating-data
    
    https://www.kaggle.com/code/swaralipibose/training-t5-model-yet-again 
    
Hello! 
In this project i have built a project to generate Questions and Answers from a piece of text . It can be very usefull teachers to create questions for their students.The project is built on top of python with the website using streamlit . 

## Explaination of the algorithm

## Data 

Code available here :- creating-data.ipynb 

The model is trained on squad dataset . The json format is converted to csv and the data has been preprocessed . For the implementation you can check the file . The squad dataset was loaded from huggingface . 

## Algorithm 

I trained a T5 model which has been released quite recently . It gave me quite good performance on the dataset . After which we use a sliding window approach to generate multple questions , window is the number of words generated by (no of words in text)/(no of questions needed) . Stride percentage denotes by what percent is the window moved . One question is generated by the model on each window . Code :- training-t5-model.ipynb and inference-of-model.ipynb the training file took almost 8 hours to run on kaggle gpu . Less stride can generate more duplicates but also more questions . 


## Deployement 

The model is deployed using streamlit . And the aretiecture and layot of the website includes a input text box below two sliders indicating the no of questions and the stride percent . Then the model generates the question every time you check a question it gets deleted from the main file . To download it a button is available at the bottom . We can also edit the question and answer in the input box itself.

## Demo 
<img src="2c31b1e8-5248-406b-877d-574eee555910.gif">
as you can see some questions still haded to be manually deleted . Also the file downloaded wasent recorder so i will just paste the screenshots :- 

<img src="Screenshot (91).png">


It produces an output file `q and a.txt` with the following contents :- 

``` 
question :- What is ML?
answer :-   Not provided
question :- What is the term for methods that leverage data to improve performance on some set of tasks?
answer :- Machine learning
question :- Machine learning algorithms build a model based on what?
answer :- sample data
question :- Machine learning algorithms are used in what kind of applications?
answer :- medicine, email filtering, speech recognition, and computer vision
question :- Machine learning is closely related to what?
answer :- computational statistics
question :- What is a related field of study?
answer :- Data mining
question :- Machine learning uses data and neural networks in a way that mimics what?
answer :- the working of a biological brain
question :- What is another term for predictive analytics?
answer :- machine learning 
``` 

the input para was :- 

``` 
Machine learning (ML) is a field of inquiry devoted to understanding and building methods that 'learn', that is, methods that leverage data to improve performance on some set of tasks.[1] It is seen as a part of artificial intelligence. Machine learning algorithms build a model based on sample data, known as training data, in order to make predictions or decisions without being explicitly programmed to do so.[2] Machine learning algorithms are used in a wide variety of applications, such as in medicine, email filtering, speech recognition, and computer vision, where it is difficult or unfeasible to develop conventional algorithms to perform the needed tasks.[3]

A subset of machine learning is closely related to computational statistics, which focuses on making predictions using computers; but not all machine learning is statistical learning. The study of mathematical optimization delivers methods, theory and application domains to the field of machine learning. Data mining is a related field of study, focusing on exploratory data analysis through unsupervised learning.[5][6] Some implementations of machine learning use data and neural networks in a way that mimics the working of a biological brain.[7][8] In its application across business problems, machine learning is also referred to as predictive analytics. 
``` 

Possible updates :- 

Converting it into a python package . Improving the Model performance . Text cleaning . Post processing. 

# Thank you! 

