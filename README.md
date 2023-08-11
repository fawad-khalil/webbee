**Minimum Node Version: 16.5 or higher**

Get started:

- create your own repo (for example on www.github.com)
- change the origin to your own repo with `git remote set-url origin <remote_url>`
- run `npm i` to install all dependencies
- change directory to whatever tech suites you best
- run `npm run migrate` (1 migration should throw an exception)
- run `npm run test` (1 test should succeed and 3 should fail due to exceptions)

Your task:

- Read the exceptions in console and go to the files where exceptions are thrown.
- In these files, you will find what you need to do to pass the test cases.

Good luck! 🍀🚀

### Unit Tests result:
```
npm run test

> express_sequelize@1.0.0 test
> jest --detectOpenHandles

 PASS  src/Modules/menu-items/menu-items.e2e.spec.ts (6.533 s)
  ● Console

    console.log
      Executing (default): SELECT 1+1 AS result

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)

    console.log
      Executing (default): SELECT `MenuItem`.`id`, `MenuItem`.`name`, `MenuItem`.`url`, `MenuItem`.`parentId`, `MenuItem`.`createdAt`, `children`.`id` AS `children.id`, `children`.`name` AS `children.name`, `children`.`url` AS `children.url`, `children`.`parentId` AS `children.parentId`, `children`.`createdAt` AS `children.createdAt` FROM `menu_item` AS `MenuItem` LEFT OUTER JOIN `menu_item` AS `children` ON `MenuItem`.`id` = `children`.`parentId`;

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)

    console.log
      [{"id":1,"name":"All events","url":"/events","parentId":null,"createdAt":"2023-08-07 22:50:31","children":[{"id":2,"name":"Laracon","url":"/events/laracon","parentId":1,"createdAt":"2023-08-07 22:50:31"},{"id":5,"name":"Reactcon","url":"/events/reactcon","parentId":1,"createdAt":"2023-08-07 22:50:31"}]},{"id":2,"name":"Laracon","url":"/events/laracon","parentId":1,"createdAt":"2023-08-07 22:50:31","children":[{"id":3,"name":"Illuminate your knowledge of the laravel code base","url":"/events/laracon/workshops/illuminate","parentId":2,"createdAt":"2023-08-07 22:50:31"},{"id":4,"name":"The new Eloquent - load more with less","url":"/events/laracon/workshops/eloquent","parentId":2,"createdAt":"2023-08-07 22:50:31"}]},{"id":3,"name":"Illuminate your knowledge of the laravel code base","url":"/events/laracon/workshops/illuminate","parentId":2,"createdAt":"2023-08-07 22:50:31","children":[]},{"id":4,"name":"The new Eloquent - load more with less","url":"/events/laracon/workshops/eloquent","parentId":2,"createdAt":"2023-08-07 22:50:31","children":[]},{"id":5,"name":"Reactcon","url":"/events/reactcon","parentId":1,"createdAt":"2023-08-07 22:50:31","children":[{"id":6,"name":"#NoClass pure functional programming","url":"/events/reactcon/workshops/noclass","parentId":5,"createdAt":"2023-08-07 22:50:31"},{"id":7,"name":"Navigating the function jungle","url":"/events/reactcon/workshops/jungle","parentId":5,"createdAt":"2023-08-07 22:50:31"}]},{"id":6,"name":"#NoClass pure functional programming","url":"/events/reactcon/workshops/noclass","parentId":5,"createdAt":"2023-08-07 22:50:31","children":[]},{"id":7,"name":"Navigating the function jungle","url":"/events/reactcon/workshops/jungle","parentId":5,"createdAt":"2023-08-07 22:50:31","children":[]}]

      at Modules/menu-items/menuItems.controller.ts:107:17

    console.warn
      (sequelize) Warning: Model "MenuItem" is declaring public class fields for attribute(s): "name", "url", "parentId".
      These class fields are shadowing Sequelize's attribute getters & setters.
      See https://sequelize.org/main/manual/model-basics.html#caveat-with-public-class-fields

      at Logger.warn (../../node_modules/sequelize/src/utils/logger.ts:41:13)
      at Timeout._onTimeout (../../node_modules/sequelize/src/model.js:102:18)

 PASS  src/Modules/events/events.e2e.spec.ts
  ● Console

    console.log
      Executing (default): SELECT 1+1 AS result

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)

    console.log
      Executing (default): SELECT `id`, `name`, `createdAt` FROM `Event` AS `Event`;

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)

    console.warn
      (sequelize) Warning: Model "Event" is declaring public class fields for attribute(s): "name".
      These class fields are shadowing Sequelize's attribute getters & setters.
      See https://sequelize.org/main/manual/model-basics.html#caveat-with-public-class-fields

      at Logger.warn (../../node_modules/sequelize/src/utils/logger.ts:41:13)
      at Timeout._onTimeout (../../node_modules/sequelize/src/model.js:102:18)

    console.log
      Executing (default): SELECT `Event`.`id`, `Event`.`name`, `Event`.`createdAt`, `workshops`.`id` AS `workshops.id`, `workshops`.`start` AS `workshops.start`, `workshops`.`end` AS `workshops.end`, `workshops`.`eventId` AS `workshops.eventId`, `workshops`.`name` AS `workshops.name`, `workshops`.`createdAt` AS `workshops.createdAt` FROM `Event` AS `Event` INNER JOIN `Workshop` AS `workshops` ON `Event`.`id` = `workshops`.`eventId`;

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)

    console.warn
      (sequelize) Warning: Model "Workshop" is declaring public class fields for attribute(s): "start", "end", "eventId", "name".
      These class fields are shadowing Sequelize's attribute getters & setters.
      See https://sequelize.org/main/manual/model-basics.html#caveat-with-public-class-fields

      at Logger.warn (../../node_modules/sequelize/src/utils/logger.ts:41:13)
      at Timeout._onTimeout (../../node_modules/sequelize/src/model.js:102:18)

    console.log
      Executing (default): SELECT `Event`.`id`, `Event`.`name`, `Event`.`createdAt`, `workshops`.`id` AS `workshops.id`, `workshops`.`start` AS `workshops.start`, `workshops`.`end` AS `workshops.end`, `workshops`.`eventId` AS `workshops.eventId`, `workshops`.`name` AS `workshops.name`, `workshops`.`createdAt` AS `workshops.createdAt` FROM `Event` AS `Event` INNER JOIN `Workshop` AS `workshops` ON `Event`.`id` = `workshops`.`eventId` WHERE `workshops`.`start` > '2023-08-11 23:04:52.808 +00:00';

      at Sequelize.log (../../node_modules/sequelize/src/sequelize.js:1274:15)


Test Suites: 2 passed, 2 total
Tests:       4 passed, 4 total
Snapshots:   0 total
Time:        8.989 s
Ran all test suites.
```
