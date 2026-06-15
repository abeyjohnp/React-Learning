**State is the data connected to html. When we update this data, it will update the html**

```jsx
const chatMessages = [{
          message : 'hello chatbot',
          sender : 'user',
          id : 'id1'
          //key is compulsory, we could give an id.
        },{
          message : 'Hello! How can I help you?',
          sender : 'robot',
          id : 'id2'
        },{
          message : 'Can you get me todays date?',
          sender : 'user',
          id : 'id3'
        },{
          message : 'Today is June 10',
          sender : 'robot',
          id : 'id4'
        }]
```
```jsx
function ChatMessages()
{
    //this array has two values
    //first value is current data
    //second value is the function that updates this data
        const array = React.useState([{
          message : 'hello chatbot',
          sender : 'user',
          id : 'id1'
          //key is compulsory, we could give an id.
        },{
          message : 'Hello! How can I help you?',
          sender : 'robot',
          id : 'id2'
        },{
          message : 'Can you get me todays date?',
          sender : 'user',
          id : 'id3'
        },{
          message : 'Today is June 10',
          sender : 'robot',
          id : 'id4'
        }]);
}
```
1. Current data (current value)
ChatMessages can change data overtime, the first value in that array gives us the current value of chatMessages which is the current data.
2. Function that updates this data. React we cannot directly update the data. We have to update through a function.

## Important Notes
1. In react we should never modify the data directly, we have to take the copy and then modify the copy.

```jsx
function sendMessage()
        {
          setChatMessages([
            ...chatMessages,
            {
              message : 'test',
              sender : 'user',
              id : crypto.randomUUID()
            }
            //we create a copy of the chatmessages array and then add this new value to the end of that array
          ]);
        }
```

**The React useState hook returns an array containing exactly two values: the current state value at index 0 and a setter function to update that state at index 1**

