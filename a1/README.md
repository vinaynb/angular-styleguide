## Single Responsibility

### Rule of 1
###### [Style [Y001](#style-y001)]

  - Define 1 component per file, recommended to be less than 400 lines of code.  

### Small Functions
  - Define small functions, no more than 75 LOC (less is better).  

**[Back to top](#table-of-contents)**

## IIFE
### JavaScript Scopes

  - Wrap Angular components in an Immediately Invoked Function Expression (IIFE).

  ```javascript
  /**
   * recommended
   *
   * no globals are left behind
   */

  // logger.js
  (function() {
      'use strict';

      angular
          .module('app')
          .factory('logger', logger);

      function logger() { }
  })();
  ```

## Controllers

### Sample Controller file
  ```javascript
  (function() {
    'use strict';

    angular
        .module('app')
        .controller('testCtrl', controller);

    controller.$inject = [];
    
  /* recommended */
  function controller() {
      var vm = this;
      
      //variables
      vm.sessions = [];
      vm.title = 'Sessions';
      
      //core
      vm.gotoSession = gotoSession;
      vm.refresh = refresh;
      vm.search = search;
      
      //helpers
      vm.checkStringForLength = checkStringForLength;
      self.checkStringForNumber = checkStringForNumber;
      
      ////////////

      function gotoSession() {
        /* */
      }

      function refresh() {
        /* */
      }

      function search() {
        /* */
      }
      
      function checkStringForLength() {
        /* */
      }
      
      function checkStringForNumber() {
        /* */
      }
  }
  })();
    
  ```
## Services
### Sample Service file  
  ```javascript
  (function() {
  'use strict';
  
  angular
        .module('cloudMasterApp')
        .controller('testService', service);

  function service($http, $location, $q, exception, logger) {
      var isPrimed = false;
      var primePromise;

      var service = {
          getAvengersCast: getAvengersCast,
          getAvengerCount: getAvengerCount,
          getAvengers: getAvengers,
          ready: ready
      };

      return service;

      ////////////

      function getAvengers() {
          // implementation details go here
      }

      function getAvengerCount() {
          // implementation details go here
      }

      function getAvengersCast() {
          // implementation details go here
      }

      function prime() {
          // implementation details go here
      }

      function ready(nextPromises) {
          // implementation details go here
      }
  }
  })();
  ```

**[Back to top](#table-of-contents)**

## Directives
### Sample Directive File  

  ```javascript
  (function() {
    'use strict';
    
    angular
      .module('app.widgets')
      .directive('testDirective', directive);

    function directive() {
        var directive = {
            link: link,
            templateUrl: '/template/is/located/here.html',
            restrict: 'EA'
        };
        return directive;

        function link(scope, element, attrs) {
          /* */
        }
    }
  })();
  ```
