# HTML TO PDF Converter Microservice

This microservice will convert HTML to PDF. The conversion will be done with [wkhtmltopdf](https://wkhtmltopdf.org/)

## Prerequisites

1. docker

## Getting Started

    $ make

## Example Request

`curl -X POST
http://localhost:8080
-H 'Content-Type: application/json'
-d '{"content":"&lt;h1&gt;Test&lt;/h1&gt;&lt;p&gt;Hello world&lt;/p&gt;","options":{ "pageSize": "letter" }}'`

- content is the HTML which should be converted
- options are optional parameters

## More facts
Simple to use HTML to PDF API.
Just send HTML content in json body request. Make sure that html you are sending is string.
You can use bootrstrap or any other design framework, but just import css file in link tag in header.
Default port on which api is located is 8080, but you can change it on any other port.
If you are using ReactJS, you can easily transform any component to string HTML, but you have to provide css of classes in tag.

Converting component to string HTML:
`import { renderToString } from "react-dom/server";
renderToString(anyComponent)`

Now you can send this string via fetch or axios instance request.
If you want to download PDF on a button click use it like this:

`const response = await pdfGenerator.post(
        "/",
        {
            content: renderToString(
                renderToString(anyComponent), //or any other HTML string
            ),
            options: { pageSize: "letter" },
        },
        {
            responseType: "blob", // blob will tell that we are wanting file to be downloaded, and not bite array
            headers: {
                Accept: "application/pdf",
            },
        }
    );`
   

## License
This is public domain.
