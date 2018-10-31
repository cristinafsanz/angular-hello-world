# angular-hello-world

First Angular App created following the steps of the [Angular 4 Tutorial: Angular 4 in 20 minutes](https://programmingwithmosh.com/angular/angular-4-tutorial/) tutorial.

- Install Angular CLI:

  ```
  npm install -g @angular/cli
  ```

- Create Angular project:

  ```
  ng new hello-world
  ```

- Run the project:

  ```
  cd hello-world
  npm install 
  ng serve
  ```

- Access the application in http://localhost:4200/.

## Component

The most fundamental building block in an Angular application is a component.

A component consists of three pieces:

- HTML markup: to render that view

- State: the data to display on the view

- Behavior: the logic behind that view. For example, what should happen when the user clicks a button.

## Example application

We are going to build an e-commerce application. 

On the home page, we’re going to display the list of products and below each product, we want to have a button for adding that product to the shopping cart. 

When we click this button, it also shows the number of products of this type in the shopping cart. 

## Creating a Component

- Run the following command in the terminal, inside the project folder:

```
ng g c product // generate component product
```

- This creates the following structure:

```
CREATE src/app/product/product.component.css (0 bytes)
CREATE src/app/product/product.component.html (26 bytes)
CREATE src/app/product/product.component.spec.ts (635 bytes)
CREATE src/app/product/product.component.ts (273 bytes)
UPDATE src/app/app.module.ts (479 bytes)
```

- hello-world/src/app/product/product.component.ts

  - selector: 'app-product' // It associates a new HTML element to this component.

- Añadir componente en src/app/app.component.html

  ```
  <app-product></app-product>
  ```

- hello-world/src/app/product/product.component.ts

  - class ProductComponent

  -  In order to attach metadata that Angular understands to this class, we need to promote this class to a component. We can do this by using the @Component() decorator function on top of this class.

    - It takes an object with the following properties:

      - selector

      - templateUrl

      - styleUrls

### Property binding

- We don’t work directly with the DOM (like Vanilla JavaScript), we use property binding.

  - Example: new field 
    ```
    export class ProductComponent {
      title = 'USB Stick 8GB';
    }
    ````

  - In product.component.html we use interpolation:

    ```
    <p>{{ title }}</p>
    ```

    - Shorthand of

    ```
    <p [innerHtml]="title"></p>
    ```

### Event binding

With event binding, we bind events of DOM elements (such as clicks) to methods in our component.

- In product.component.html:

  ```
  <button (click)="addItem()">Add</button>
  ```

- In product.component.ts:

  ```
  addItem() { 
      this.itemCount++;
   }
  ```
