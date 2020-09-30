# Meal-Maker

const menu = {
  _courses: {
    appetizers: [],
    mains: [],
    desserts: []
  },
get appetizers() {
  return this._courses.appetizers;
},
set appetizers(appetizers) {
  return this._courses.appetizers = appetizers;
},
get mains(){
  return this._courses.mains;
},
set mains(mains){
  this._courses.mains = mains;
},
get desserts(){
  return this._courses.desserts;
},
set desserts(desserts) {
  this._courses.desserts = desserts;
},
get courses() {
  return {
    appetizers: this.appetizers,
    mains: this.mains,
    desserts: this.desserts,
  }
},
addDishToCourse(courseName, dishName, dishPrice) {
  const dish = {
    name: dishName,
    price: dishPrice,
  };
  this._courses[courseName].push(dish);
},
getRandomDishFromCourse(courseName) {
  const dishes = this._courses[courseName];
  const randomIndex = Math.floor(Math.random() * dishes.length);
    return dishes[randomIndex];
},
generateRandomMeal(){
  const appetizer = this.getRandomDishFromCourse('appetizer');
  const mains = this.getRandomDishFromCourse('mains');
  const desserts = this.getRandomDishFromCourse('desserts');
  const totalPrice = appetizer.price + main.price + dessert.price;
    return `Your meal is ${appetizer.name}, ${main.name}, and ${dessert.name}, and the total price is ${totalPrice}.`;
}
};

menu.addDishToCourse('appetizers', 'salad', 7.44);
menu.addDishToCourse('appetizers', 'wings', 7.44);
menu.addDishToCourse('appetizers', 'breadsticks', 7.44);

menu.addDishToCourse('mains', 'steak', 18.00);
menu.addDishToCourse('mains', 'lobster', 18.00);
menu.addDishToCourse('mains', 'chicken', 18.00);

menu.addDishToCourse('desserts', 'cake', 8.50);
menu.addDishToCourse('desserts', 'moose', 8.50);
menu.addDishToCourse('desserts', 'ice cream', 8.50);

const meal = menu.generateRandomMeal();
console.log(meal);
