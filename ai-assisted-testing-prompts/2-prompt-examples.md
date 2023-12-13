# Prompt examples
These prompts can be used to practise different prompting tactics within the context of testing.

## Delimiters
You are a SQL data generator. Generate five rows of SQL for a MySQL database. 

* The table name is identified with a # sign. 
* Each table column is identified with a % sign
* Each column is described in order of name, data type and data options using the | sign
* If a column data option says random. Randomize data based on the suggested format and column name

Here are the instructions:

\# rooms

% room_name | string | random

% type | string |  'single' or 'double'

% beds | integer | 1 to 6

% accessible | boolean | true or false

% image | string | random url

% description | string | random max 20 characters

% features | array[string] | 'Wifi', 'TV' or 'Safe'

% roomPrice |  integer | 100 to 200

## Structured output
Create a JSON object with random data that contains the following fields: firstname, lastname, totalprice, deposit paid. Also, include an object called booking dates that contains checkin and checkout dates.

## Check for assumptions
You will be provided with a JSON object delimited by three hashes. Extract all emails that end with .com and write them out as a list.

If no email addresses with a .com email address exist, simply write "No .com emails found"

\###

[{
  "firstname": "Bret",
  "lastname": "Averay",
  "email": "baveray0@apple.com"
}, {
  "firstname": "Annabel",
  "lastname": "Biswell",
  "email": "abiswell2@nsw.gov.au"
}, {
  "firstname": "Pavel",
  "lastname": "Itzhaki",
  "email": "pitzhaki3@pagesperso-orange.fr"
}, {
  "firstname": "Pail",
  "lastname": "Yandell",
  "email": "pyandell4@ning.com"
}, {
  "firstname": "Glennis",
  "lastname": "Pentecost",
  "email": "gpentecost6@yelp.com"
}]

\###

## Few shot prompting
You are an expert exploratory tester. Create three test charters for a booking system that focus on the risks around booking dates. The format should follow: Explore <Target> using <Resource> to discover <Information>

For example:
* Explore user permissions using different users to discover permission issues
* Explore browser animations using different devices to discover how animations render

## Specify steps to complete
You are going to be given a list of instructions to follow.

1 - Identify functional risks that might impact the text delimited by three hashes
2 - Convert the risks into test charters
3 - Format each charter into a Discover <feature> using <resource> to discover <information> format

###
As a user
I want to be able to calculate my tax
So I know what tax I have to pay
###

## Work out a solution
You are a software developer in test that is experienced in writing Java. Create a unit test for the following method:

```Java 
public class AuthService {

  public HttpStatus deleteToken(Token token) throws SQLException {
    Boolean successfulDeletion = authDB.deleteToken(token);

    if(successfulDeletion){
      return HttpStatus.OK;
    } else {
      return HttpStatus.NOT_FOUND;
    }
  }

}
```
