BindingResult
------------- 
This is Spring’s object that holds the result of the validation and binding and contains errors that may have occurred. The BindingResult must come right after the model object that is validated or else Spring will fail to validate the object and throw an exception.

Each complex object Request is validated, if any validators are defined in the Controller. 

Validation happens when the BindingAwareModelMap object is formed. When the request is completed, again the BindingAwareModelMap object needs to be updated with the resulting attributes. At this point, check is done to see if the attribute object is validated. If not validated, validators are used to validate them and the corresponding BindingResult is added to the BindingAwareModelMap.
