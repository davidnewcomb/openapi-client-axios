# OpenAPI Frontend
[![Build Status](https://travis-ci.org/anttiviljami/openapi-frontend.svg?branch=master)](https://travis-ci.org/anttiviljami/openapi-frontend)
[![npm version](https://img.shields.io/npm/v/openapi-frontend.svg)](https://www.npmjs.com/package/openapi-frontend)
[![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/anttiviljami/openapi-backend/blob/master/LICENSE)
[![Sponsored](https://img.shields.io/badge/chilicorn-sponsored-brightgreen.svg?logo=data%3Aimage%2Fpng%3Bbase64%2CiVBORw0KGgoAAAANSUhEUgAAAA4AAAAPCAMAAADjyg5GAAABqlBMVEUAAAAzmTM3pEn%2FSTGhVSY4ZD43STdOXk5lSGAyhz41iz8xkz2HUCWFFhTFFRUzZDvbIB00Zzoyfj9zlHY0ZzmMfY0ydT0zjj92l3qjeR3dNSkoZp4ykEAzjT8ylUBlgj0yiT0ymECkwKjWqAyjuqcghpUykD%2BUQCKoQyAHb%2BgylkAyl0EynkEzmkA0mUA3mj86oUg7oUo8n0k%2FS%2Bw%2Fo0xBnE5BpU9Br0ZKo1ZLmFZOjEhesGljuzllqW50tH14aS14qm17mX9%2Bx4GAgUCEx02JySqOvpSXvI%2BYvp2orqmpzeGrQh%2Bsr6yssa2ttK6v0bKxMBy01bm4zLu5yry7yb29x77BzMPCxsLEzMXFxsXGx8fI3PLJ08vKysrKy8rL2s3MzczOH8LR0dHW19bX19fZ2dna2trc3Nzd3d3d3t3f39%2FgtZTg4ODi4uLj4%2BPlGxLl5eXm5ubnRzPn5%2Bfo6Ojp6enqfmzq6urr6%2Bvt7e3t7u3uDwvugwbu7u7v6Obv8fDz8%2FP09PT2igP29vb4%2BPj6y376%2Bu%2F7%2Bfv9%2Ff39%2Fv3%2BkAH%2FAwf%2FtwD%2F9wCyh1KfAAAAKXRSTlMABQ4VGykqLjVCTVNgdXuHj5Kaq62vt77ExNPX2%2Bju8vX6%2Bvr7%2FP7%2B%2FiiUMfUAAADTSURBVAjXBcFRTsIwHAfgX%2FtvOyjdYDUsRkFjTIwkPvjiOTyX9%2FAIJt7BF570BopEdHOOstHS%2BX0s439RGwnfuB5gSFOZAgDqjQOBivtGkCc7j%2B2e8XNzefWSu%2BsZUD1QfoTq0y6mZsUSvIkRoGYnHu6Yc63pDCjiSNE2kYLdCUAWVmK4zsxzO%2BQQFxNs5b479NHXopkbWX9U3PAwWAVSY%2FpZf1udQ7rfUpQ1CzurDPpwo16Ff2cMWjuFHX9qCV0Y0Ok4Jvh63IABUNnktl%2B6sgP%2BARIxSrT%2FMhLlAAAAAElFTkSuQmCC)](http://spiceprogram.org/oss-sponsorship)

JavaScript library for consuming OpenAPI-enabled APIs

Also see: [openapi-backend](https://github.com/anttiviljami/openapi-backend)

## Features

- [x] Create API clients by describing them in [OpenAPI specification](https://github.com/OAI/OpenAPI-Specification)
and importing them via YAML or JSON files or by just passing an object
- [x] Call API operations with your preferred syntax:
  - `client.updatePet(1, pet)` - operation methods
  - `client.query('updatePet', 1, pet)` - query method
  - `client.put('/pets/1', pet)` - axios method aliases
  - `client({ method: 'put', url: '/pets/1', data: pet })` - axios basic
- [x] Built on top of the robust [axios](https://github.com/axios/axios) JavaScript library
- [x] Isomorphic, works both in browser and Node.js

## Quick Start

```
npm install --save openapi-frontend
```

With promises / CommonJS syntax:

```javascript
const OpenAPIFrontend = require('openapi-frontend').default;

const api = new OpenAPIFrontend({ definition: 'http://example.com/api/openapi.json' });
api.init()
  .then(client => client.getPetById(1))
  .then(res => console.log('Here is pet id:1 from the api', res));
```

With async-await / ES6 syntax:

```javascript
import OpenAPIFrontend from 'openapi-frontend';

const api = new OpenAPIFrontend({ definition: 'http://example.com/api/openapi.json' });
api.init();

async function createPet() {
  const res = await api.client.createPet({ name: 'Garfield' });
  console.log('Pet created', res);
}
```

## Contributing

OpenAPI Backend is Free and Open Source Software. Issues and pull requests are more than welcome!

[<img alt="The Chilicorn" src="http://spiceprogram.org/assets/img/chilicorn_sticker.svg" width="250" height="250">](https://spiceprogram.org/oss-sponsorship)

