
### Flexible Basic Concepts

While a discussion of flexible boxes, it requires a new terminology

![Flexbox model]({{ "assets/images/flex_terms.png" }})

* **Flex container**: is the parent element in which flex items are contained.

* **Flex item**: each child of a flex container becomes a flex item. Text is wrapped in an anonymous flex item.

<!-- next-slide -->

Every flexible box layout follows two axes:

The **main axis**: the axis along which the flex items follow each other

The **cross axis**: the axis perpendicular to the main axis

<!-- next-slide -->

Flexbox properties:

* The **```flex-direction```** establishes the orentation of main axis: **```row```** or **```column```**

* The **```justify-content```** defines how flex items are laid out along the **main axis**

* The **```align-items```** defines for how flex items are laid out along the **cross axis**

* The **```align-self```** defines how a **single** flex item is aligned on the **cross axis**, and **overrides the default** established by **align-items**

<!-- next-slide -->

* The **```order```** determines which elements appear first

* The **```flex-wrap```** define if flex items are forced into a **single line** or can be wrapped onto **multiple lines**

* The **```flex-grow```** specifies what amount of space **inside** the flex container the item should take up

* The **```flex-shrink```** specifies the flex shrink factor of a flex item

* The **```flex-basis```** specifies the **flex basis** which is the initial **main size** of a flex item

<!-- next-slide -->

