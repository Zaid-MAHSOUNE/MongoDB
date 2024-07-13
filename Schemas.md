### Data Types

1. **String:**
   - Represents textual data.
   - Example:
     ```js
     name: {
       type: String,
       required: true
     }
     ```

2. **Number:**
   - Represents numerical data, including integers and floats.
   - Example:
     ```js
     age: {
       type: Number,
       min: 0,
       max: 120
     }
     ```

3. **Date:**
   - Represents date and time values.
   - Example:
     ```js
     createdAt: {
       type: Date,
       default: Date.now
     }
     ```

4. **Boolean:**
   - Represents true or false values.
   - Example:
     ```js
     isActive: {
       type: Boolean,
       default: true
     }
     ```

5. **Array:**
   - Represents a list of items. The type of items in the array can be specified.
   - Example:
     ```js
     tags: [String]
     ```

6. **Buffer:**
   - Represents binary data.
   - Example:
     ```js
     profilePicture: Buffer
     ```

7. **ObjectId:**
   - Represents a MongoDB ObjectId, typically used for referencing other documents.
   - Example:
     ```js
     userId: {
       type: mongoose.Schema.Types.ObjectId,
       ref: 'User'
     }
     ```

8. **Mixed:**
   - Represents any data type. Use sparingly, as it bypasses schema validation.
   - Example:
     ```js
     additionalInfo: mongoose.Schema.Types.Mixed
     ```

9. **Map:**
   - Represents a map of key-value pairs.
   - Example:
     ```js
     metaData: {
       type: Map,
       of: String
     }
     ```

### Schema Properties

1. **required:**
   - Indicates that a field must be provided.
   - Example:
     ```js
     email: {
       type: String,
       required: true
     }
     ```

2. **default:**
   - Specifies a default value if none is provided.
   - Example:
     ```js
     createdAt: {
       type: Date,
       default: Date.now
     }
     ```

3. **unique:**
   - Ensures that each value in the field is unique across the collection.
   - Example:
     ```js
     username: {
       type: String,
       unique: true
     }
     ```

4. **min and max:**
   - Sets the minimum and maximum values for numbers and dates.
   - Example:
     ```js
     age: {
       type: Number,
       min: 0,
       max: 120
     }
     ```

5. **enum:**
   - Restricts the value of a field to a specified set of values.
   - Example:
     ```js
     status: {
       type: String,
       enum: ['active', 'inactive', 'pending']
     }
     ```

6. **match:**
   - Validates the field value against a regular expression.
   - Example:
     ```js
     email: {
       type: String,
       match: /^[^\s@]+@[^\s@]+\.[^\s@]+$/
     }
     ```

7. **minlength and maxlength:**
   - Sets the minimum and maximum length for string fields.
   - Example:
     ```js
     password: {
       type: String,
       minlength: 8,
       maxlength: 128
     }
     ```

8. **validate:**
   - Allows custom validation logic.
   - Example:
     ```js
     phoneNumber: {
       type: String,
       validate: {
         validator: function(v) {
           return /\d{3}-\d{3}-\d{4}/.test(v);
         },
         message: props => `${props.value} is not a valid phone number!`
       }
     }
     ```

### Example Schema with Various Data Types and Properties

```js
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    minlength: 3,
    maxlength: 100
  },
  age: {
    type: Number,
    min: 0,
    max: 120
  },
  email: {
    type: String,
    required: true,
    unique: true,
    match: /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  },
  password: {
    type: String,
    minlength: 8,
    maxlength: 128
  },
  profilePicture: Buffer,
  isActive: {
    type: Boolean,
    default: true
  },
  roles: [String],
  metaData: {
    type: Map,
    of: String
  },
  createdAt: {
    type: Date,
    default: Date.now
  },
  updatedAt: Date,
  tags: {
    type: [String],
    enum: ['admin', 'user', 'guest']
  }
});
```
