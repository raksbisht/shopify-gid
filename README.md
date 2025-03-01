# shopify-gid
Universal encoder/decoder for ID values returned from the Shopify Storefront
GraphQL API. **400 bytes gzipped.**

### ✅ Added Support for [Non-encoded object IDs](https://shopify.dev/docs/api/release-notes/2022-04#non-encoded-object-ids-in-the-graphql-storefront-api) in the GraphQL Storefront API 


## Install
```bash
npm i shopify-gid --save
```

# Usage
```javascript
import { encode, decode } from 'shopify-gid'
```
## decode(base64hash) OR decode(globalID)
```javascript
decode('Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0LzEyMzQ1...')
        //OR
decode('gid://shopify/Product/12345')
  // => { type: 'Product', id: '12345', params: { accessToken: 'abcde123' }, raw: 'Z2lkOi8...' }
```
## encode(type, id[, params])
```javascript
encode('Product', 12345, { accessToken: 'abcde123' })
  // => Z2lkOi8vc2hvcGlmeS9Qcm9kdWN0LzEyMzQ1...
```

## License
MIT License © [Eric Bailey](https://estrattonbailey.com)
