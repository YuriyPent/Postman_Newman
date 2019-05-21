NEWMAN
--
* To run Newman, ensure that you have Node.js >= v6. [Install Node.js](https://nodejs.org/en/download/package-manager/) via package manager
* Install newman: `npm install -g newman`
* In case SSL certificate error when running Npm on Windows, use: `npm config set strict-ssl false`
* Install newman reporter: `npm install -g newman-reporter-html`
* Change directory: `cd postman`
* Run newman: `newman run postman_collection.json -d postman_environment.json -r html`
* Install htmlextra reporter: `npm install -g newman-reporter-htmlextra`
* Run newman: `newman run postman_collection.json -d postman_environment.json -r htmlextra`
* Run newman with darkTheme htmlextra reporter: `newman run postman_collection.json -d postman_environment.json -r htmlextra --reporter-htmlextra-darkTheme`
* Run newman with 10 iteration: `newman run postman_collection.json -d postman_environment.json -n 10 -r htmlextra`