# Gibbon-pdf

Generate PDF with Template and JSON Schema.

Project status: [POC](https://en.wikipedia.org/wiki/Proof_of_concept)

Screencast: https://www.youtube.com/watch?v=2M10x76f6c8

## Why this project?

- I would like to move PDF generation from my application in a separate service
- I would like to allow humans to generate PDF manually, via a simple application plugged to the same API.
- I would like to keep a history (optionally) of all document generated

## Roadmaps

- [x] Integrate [`mozilla-services/react-jsonschema-form`](https://github.com/mozilla-services/react-jsonschema-form)
- [x] Integrate [`puppeteer`](https://github.com/GoogleChrome/puppeteer/)
- [x] Docker Image (`harobed/poc-generate-pdf-with-html-template-and-jsonschema:latest`)
- [x] curl example
- [x] Screencast
- [ ] Add S3 upload option
- [ ] Add [UISchema](https://react-jsonschema-form.readthedocs.io/en/latest/) support
- [ ] Check json input with JSON Schema
- [ ] Test frontend
- [ ] Configure CI
- [ ] Swagger
- [ ] Add option to save generated pdf (in PostgreSQL)

## Features

- Generate PDF file from:
  - HTML template
  - Json field values (validated by [JSON Schema](https://json-schema.org/))
- Rest API endpoints to generate html preview or PDF
- Web UI to generate PDF manually:
  - HTML form are autogenerated by [JSON Schema](https://json-schema.org/)
  - User can preview the document or generate the PDF
- Optionnaly record all PDF generation

## This project is based on this stack

- [Backend](backend/):
  - [NodeJS](https://nodejs.org/en/) with [Koa](https://koajs.com/)
  - [Nunjucks](https://mozilla.github.io/nunjucks/) to fill PDF Html templates
  - [puppeteer](https://github.com/GoogleChrome/puppeteer) to rendering PDF documents (Chrome Engine)
- [Frontend](frontend/)
  - [ReactJS](https://en.reactjs.org/), [Axios](https://github.com/axios/axios), [React-router](https://github.com/ReactTraining/react-router)
  - [react-jsonschema-form](https://github.com/mozilla-services/react-jsonschema-form) to generate Form from JSON Schema (need Bootstrap version `v3.3.6`)
  - [Bootstrap](https://getbootstrap.com/)
- Tooling
  - [Jest](https://jestjs.io/) and [supertest](https://github.com/visionmedia/supertest) for backend tests
  - [ESLint](https://eslint.org/)

## FAQ

### How can I enable Authentication system?

This project hasn't build-in authentication system, it's a internal service in your stack,
you must protect it by a private network or [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) system.

### Why « Gibbon-pdf » name?

[Gibbon](https://en.wikipedia.org/wiki/Gibbon) as an allusion to [Mandrill App](https://mandrill.com/).

---

Invoice examples:

- https://www.sparksuite.com/open-source/invoice.html

Compare with other projects:

- [athenapdf](https://github.com/arachnys/athenapdf)