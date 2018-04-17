---
layout: post
title: Working with AJAX
category: JQuery
description: A quick intro to using AJAX to save data on the fly without a page refresh.
---

## What is AJAX?

AJAX stands for Asynchonous Javascript and XML. It allows web applications to request and update data in the background without reloading the page. I will cover the jQuery implementation of AJAX as it is the easiest and most widely used.

## Retrieving Data with AJAX

The basic structure of an AJAX call involves the following elements:
- *type* of request (GET, POST, PUT, DELETE - HTTP Request Methods)
- *url* to where we can retrieve or store the data
- *dataType* of the data (JSON, XML, etc)
- *data* content or value we are sending or retrieving, consistent with the *dataType*

It is also good to add the following for good practice:
- *error* function to run if the request fails
- *success* function to run if the request works
- *timeout* for the function in milliseconds - we dont want this to go on for too long


Here is an example of data being retrieved from myData url. This url outputs data in JSON format.
If we are able to retrieve the data, the success functions runs. Otherwise the error function outputs a fail message.

```javascript
 $.ajax({
    type: "GET", 
    url: '/myData/',
    dataType: 'JSON',
    success: function(data){
        for (var key in data) {
            if (data.hasOwnProperty(key)) {
                console.log('Function Triggered');
              var htmlData = '<div class="col-md-3"><img class="img-thumbnail thumb-resize" src="/uploads/store/'+  data[key].image["thumb"].id + '" alt="'+ data[key].name +'" /></div>';
              targetDiv.find('.modal-body').append(htmlData);                
            }
        }
     },
     error: function(xhr, status, error) {
        var emptyResponseMessage = "<p>Failed to Retrieve Data</p>"
        targetDiv.find('.modal-body').append(emptyResponseMessage);
        console.log(emptyResponseMessage);
    	}
    });
```

## Deleting Data

Same as before but much simpler. The "data" itself is the ID of the post, comment, item you are deleting and its passed in the url itself.

```javascript
$.ajax({
    url: myData + myID,
    type: 'DELETE',
    success: //do something,
    error: //do something
});
```

A snippet for rails, within your data loop:

```ruby
<%= link_to 'Delete', page, class: 'btn btn-danger', remote: true, method: :delete, data: {confirm: 'Are you sure you want to delete this page?'} %>
```
                    
Reference: https://api.jquery.com/jquery.ajax/