# Business-contract-validation

### Project Title : Business Contract Validation

### NAME: Harsh Kalburgi

### Idea:

-   The user registers on our website, uploads the template for comparison, then submits the contract to be processed.
-   In order to find deviations, they can either utilize a standard template or upload a former contract that was previously affiliated with the same company as the present contract.  
-   Following their upload, the contract and template are kept in cloud storage. Because Cloudinary offers secure URLs that are impervious to data leaks, we have utilized it to store user photos along with all of their contracts. After that, the contract is parsed, and its text and entities are taken out.  
-   After that, the contract and template urls are sent to Django Backend, where they are downloaded and momentarily stored.
-   The initial element We are now using PDF Parser. To extract texts, it parses the PDF. This component receives both the contract and the template, providing us with the extracted text of both.  
-   After that, entity extraction takes place. To extract the entities contained in the contract, such as the parties' names and organizations, financial information, the length of the contract, and so forth, a Name Entity Recognition (NER) model is utilized. This module aids in identifying the principal parties to the agreement.
-   Text classification is the third element. First, terms are taken out of the template and the contract. The semantics of the sentences are compared between the clauses in the two pdfs using Levenshtein distance. The subclauses are then categorized into the appropriate clauses once the clauses have been established.  
-   After the subclauses have been classified, the collected data is submitted to an LLM, which compares the contract data with the template data to produce a textual result of any deviations that are found.  
-   After that, the deviations are noted in the PDF, which is then saved once more at the cloud service provider along with the secure link.  
-   Lastly, the user receives a report outlining the extracted items and deviations.
-   Thus, the NodeJS Backend receives information from the Django side about entities identified, deviations found, summaries, and the URL of the highlighted PDF, and then returns the response to the React Frontend for delivery to the user.
-   In addition to downloading the contract and the highlighted contract for later use, the user can read the items that have been sent to him.  
  
 
  

### Note : You may encounter errors while finding deviations. It depends on the API key you use. The current API key is of free plan and thus may lead to some missing deviations. A paid API key will perform more efficiently.

# Steps to run:

### Head to Node backend and start the server.

```bash
$ cd /L5_Backend/Node
$ npm install
$ npm index
```

### Head to Django backend and start the server.

```bash
$ cd /L5_Backend/Django
$ pip install -r requirements.txt
$ python manage.py runserver
```


### Head to React frontend and start the development server.

```bash
$ cd /L6_Frontend/
$ npm install
$ npm run start
```

# Thank You !!!


