# Mediator [⬈](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#mediatorpatternjavascript)

### Description
The dictionary refers to a mediator as a neutral party that assists in negotiations and conflict resolution. In our world, a mediator is a behavioral design pattern that allows us to expose a unified interface through which the different parts of a system may communicate.

A real-world analogy could be a typical airport traffic control system. A tower (Mediator) handles what planes can take off and land because all communications (notifications being listened out for or broadcast) are done from the planes to the control tower, rather than from plane-to-plane. A centralized controller is key to the success of this system and that's really the role a Mediator plays in software design.

Another analogy would be DOM event bubbling and event delegation. If all subscriptions in a system are made against the document rather than individual nodes, the document effectively serves as a Mediator. Instead of binding to the events of the individual nodes, a higher level object is given the responsibility of notifying subscribers about interaction events.

### Example
```javascript
var orgChart = {
  addNewEmployee: function() {
    // getEmployeeDetail provides a view that users interact with
    var employeeDetail = this.getEmployeeDetail();
    // when the employee detail is complete, the mediator (the 'orgchart' object)
    // decides what should happen next
    employeeDetail.on("complete", function(employee) {
      // set up additional objects that have additional events, which are used
      // by the mediator to do additional things
      var managerSelector = this.selectManager(employee);
      managerSelector.on("save", function(employee) {
        employee.save();
      });
    });
  },
}
```
