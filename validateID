function validateIDNumber(idNumber) {
  // Check if the input is a string or a number
  if (typeof idNumber !== "string" && typeof idNumber !== "number") {
    return false;
  }
  
  // Convert input to string and remove any non-numeric characters
  var id = idNumber.toString().replace(/[^0-9]/g, "");
  
  // Check that the ID number is 9 digits long
  if (id.length !== 9) {
    return false;
  }
  
  // Calculate the check digit
  var sum = 0;
  for (var i = 0; i < 8; i++) {
    var digit = parseInt(id.charAt(i));
    var weight = (i % 2 == 0) ? 1 : 2;
    var product = digit * weight;
    sum += (product > 9) ? product - 9 : product;
  }
  var checkDigit = (10 - (sum % 10)) % 10;
  
  // Check if the check digit matches the last digit of the ID number
  return checkDigit === parseInt(id.charAt(8));
}
