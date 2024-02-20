# Chapter 9 - Forms and Inputs
---

Introduced: the `<form>` element. The `action` attribute is to where to send the information.
The  `method` attribute is the HTTP method. In this case we use the `GET https://httpbin.org/get`,
but usually this will be a `POST https://<our-website>`

Inside forms we have `<label>` and `<input>` elements mostly.  Every input should have a label.
The `for` attribute of the label must correspond to the `id` element of the input, and the `name`
of the input is also recommended to have the same value. The `name` element is how it's sent to the server,
I mean the name of the HTTP parameter.

The `<input>` elements has many types: text, tel, password, number, and more.  There are several attributes also, 
such as `required`, `autocomplete`, etc. Look inside.

`<select>` element is a drop-down list. Inside you have `<option>` elements, which can be enclosed in `<optgroups>`.

The `select` element can have the `multiple` attribute, so that the user can choose several values.

`<fieldset>` - when your form starts to get big, it's nice to organize it in fieldsets. 

`radio` type of input is radio buttons. Having several of these share the same `name` means that only one of them can 
be selected. `checkbox` is similar.

`<textarea>` allows you to have a large text area for the user to fill in.

Finally, we have the `<button type="submit">`, which will submit the form.

This is the response from `httpbin.org`:
```
{
  "args": {
    "decade": "1980", 
    "firstName": "Yoav", 
    "food": "pizza", 
    "lastName": "Klein", 
    "message": "My Message", 
    "password": "231321", 
    "pets": [
      "dogs", 
      "cats"
    ], 
    "phone": "0505419589"
  }, 
  "headers": {
    "Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7", 
    "Accept-Encoding": "gzip, deflate, br", 
    "Accept-Language": "en-US,en;q=0.9", 
    "Host": "httpbin.org", 
    "Referer": "http://127.0.0.1:5500/", 
    "Sec-Ch-Ua": "\"Not A(Brand\";v=\"99\", \"Google Chrome\";v=\"121\", \"Chromium\";v=\"121\"", 
    "Sec-Ch-Ua-Mobile": "?0", 
    "Sec-Ch-Ua-Platform": "\"Windows\"", 
    "Sec-Fetch-Dest": "document", 
    "Sec-Fetch-Mode": "navigate", 
    "Sec-Fetch-Site": "cross-site", 
    "Sec-Fetch-User": "?1", 
    "Upgrade-Insecure-Requests": "1", 
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36", 
    "X-Amzn-Trace-Id": "Root=1-65d48456-78ddd1f346568fe24ff4d573"
  }, 
  "origin": "95.86.76.90", 
  "url": "https://httpbin.org/get?firstName=Yoav&lastName=Klein&password=231321&phone=0505419589&decade=1980&food=pizza&pets=dogs&pets=cats&message=My+Message"
}
```

You can see the `args` section, which contains a map of all the inputs of the form. The keys of this map
correspond to the `name` attributes of the inputs.

We have another `submit` button, but this time we change the form action and method, using the `formaction` and `formmethod` attributes. We use
that to send the form as a POST HTTP message to `httpbin.org/post`.

NOTE that the inputs when you use a GET request are in the URL arguments, and when you use a POST request they are in 
the HTTP body.