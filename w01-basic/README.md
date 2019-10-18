# Example 01 - Basic Programming with NodeJS

To start our workshop we prepared some examples with basic sintax and NodeJS programming model. Login to AWS Lambda Console and let's start to create our first Lambda function to validate our enviroment:

### 1. Open your Lambda console and click "Create Function"

![image](images/01.png) 

### 2. Name your function ex. w01-basic

![image](images/02.png) 

### 3. You should see the following sample code. Let's run this code by clicking on "Test"

![image](images/03.png) 

### 4. It will ask you to configure a set of parameters to execute your program. At this point we don't need to set anything, so let's keep the standard by naming it as "test1" clicking "Create".

![image](images/04.png) 

### 5. Click "Test" again and then you should see the following output

![image](images/05.png) 

### 6. Now let's see a leap year example. Check the code bisiesto and to run it change the Handler Field to "*basic.bisiesto*".

```javascript
'use strict';

module.exports.handler = async (event) => {
  return {
    statusCode: 200,
    body: JSON.stringify({
      message: 'Go Serverless v1.0! Your function executed successfully!',
      input: event,
    }, null, 2),
  };
};

module.exports.bisiesto = async (event) => {
  var ano = 2000;
  var bisiesto = false;
  if((ano%4==0 && ano%100!=0) || ano%400==0) bisiesto = true;
  return {
    statusCode: 200,
    body: JSON.stringify({
      message: 'Año ' + ano + (bisiesto ? " és bisiesto." : " no és bisiesto."),
      input: event,
    }, null, 2),
  };
};
```

![image](images/06.png) 

### 7. The default leap year output should be:

![image](images/07.png) 
