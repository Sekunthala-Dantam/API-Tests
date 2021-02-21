# API-Tests

tests["Status code is 200"] = responseCode.code === 200;


tests["Body matches string"] = responseBody.has("Starlink-19 (v1.0)");


var schema = {
 "items": {
 "type": "boolean"
 }
};
var recovery_attempt = [true, false];
var recovered = [true, false];

tests["Valid Data1"] = tv4.validate(recovery_attempt, schema);
tests["Valid Data2"] = tv4.validate(recovered, schema);
console.log("Validation failed: ", tv4.error);

tests["Content-Type is present"] = postman.getResponseHeader("Content-Type");
