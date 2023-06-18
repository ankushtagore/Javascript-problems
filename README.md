# Javascript-problems
JS problems and solutions


const obj = {
  name: 'John',
  age: 30,
  address: {
    street: '123 Main St',
    city: 'New York',
    country: {
     deepAddress: {
    street: '123 Main St',
    city: 'New York',
    country: 'USA'
  },
    }
  },
  hobbies: ['reading', 'painting']
};


function flattenObj(s, prefix='') {
let fo = {}

for (let key in s) {
if (s.hasOwnProperty(key)) {

if (typeof s[key] == "object" && s[key] !== null) {
let nested = flattenObj(s[key], prefix  + '.')
fo = {...nested, ...fo}
}
else 
{
/* console.log("obj[key]", obj[key]) */
fo[prefix + key] = s[key]
}
}
}
return fo
} 

const flattenedObj = flattenObj(obj);
console.log(flattenedObj);

