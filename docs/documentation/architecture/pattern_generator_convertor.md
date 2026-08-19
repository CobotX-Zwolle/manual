
[Github Repo](https://github.com/CobotX-Zwolle/pattern_generator_convertor)

### Currently:

* Pattern Generator UI generates an JSON with all the info filled in
* The python script converts this all into .yamls to be used by the cpp program
* yamls can still be edited easily afterwards

### Future
* Direct interpertation of the JSON file(s) by the cpp code

#### Info in the JSON:
* Pallet info
    * Size
    * Location
* Gripper info
    * Type
    * Size
    * Groups
* Product info
    * Name
    * Size
    * Weight
    * Label
* Pick-up
    * Location
    * Gripper approach and exit
    * Nr of products and which
* Pattern info
    * Product, gripper and pick-up combination
    * Location and order on the pallet
    * Approach and exit vectors
