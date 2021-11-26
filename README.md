# axios-bug-example
The repository provides an example for inconsistent axios behaviour

## How to Use
To test it, clone the repository locally:
```bash
git clone git@github.com:MaximKalinin/axios-bug-example.git
cd axios-bug-example
yarn install
yarn start
```
Then open http://localhost:1234 in your browser and check network tab in developer tools panel.

## Description of Problem
The code can be found in `public/index.html` file. It demonstrates how default axios instance treats relative URLs and Object-URLs vs how custom axios instance (created with `axios.create(...)`) treats relative URLs and Object-URLs.

You will see that one of requests has failed with 404 error. If you check the request URL, you will see something like `http://localhost:1234/blob:http://localhost:1234/a70472e6-3d4e-4b8f-9fda-5e5dbd1b8bff` which is the Object-URL appended to `baseUrl`, but expected request URL is `blob:http://localhost:1234/a70472e6-3d4e-4b8f-9fda-5e5dbd1b8bff`.
