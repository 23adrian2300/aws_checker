# AWS::IAM::ROLE Policy Checker
This is a solution to a recruitment task for Remility company.

## Task
Write a method verifying the input JSON data. Input data format is defined as AWS::IAM::Role Policy - definition and example (AWS IAM Role JSON definition and example). Input JSON might be read from a file. 
Method shall return logical false if an input JSON Resource field contains a single asterisk and true in any other case. 

## How to run
First, you need to download the repository with the solution using the command:

`git clone https://github.com/23adrian2300/AWS_Validity_Task.git`

Then, you need to navigate to the folder with the downloaded code:

`cd AWS_Validity_Task`


To run the main file, you need to use:

`python main.py`

To run the test, use the following command:

`python test_functions.py`

## How it works


First, the user provides a file path. Then, we first check if it is a .json file, and then if it is a valid JSON. Next, we verify if it is an AWS::IAM::Role Policy by checking if the appropriate keys are present. Additionally, we check cases such as the length and pattern of the name.
If we pass the verification successfully, we proceed to the main function, which, knowing that it deals with valid JSON, checks if there is only a single '*' character in the "Resource" field. 
In that case, we return False. In any other case, for example: '**', 'p', '121', we return True.

## Valid JSON Format
```json
{
    "PolicyName": "root",
    "PolicyDocument": {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "IamListAccess",
                "Effect": "Allow",
                "Action": [
                    "iam:ListRoles",
                    "iam:ListUsers"
                ],
                "Resource": "*"
            }
        ]
    }
}
```
