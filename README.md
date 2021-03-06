
## ghw-drawer

Github Worlds drawer is a visualization toolkit that provides
**Views** into JSON data that comes from the
[Github GraphQL API](https://developer.github.com/v4/).
It is called Github Worlds **drawer** because there is also a
**[Github Worlds menu](https://muitool.github.io/ghw-menu/)** which displays the same data and views
but with the
**[Menu](https://material-ui.com/demos/menus/)**
being the primary navigation element instead of the
**[Drawer](https://material-ui.com/demos/drawers/)**

This demo is an extension of
[mui-drawer](https://stormasm.github.io/mui-drawer/) and it is assumed that you have already reviewed the concepts and
documentation associated with that repo.

### A Data Visualization Framework

We are in the process of developing a simple generic data visualization
framework in the context of a
**[Material-UI Tutorial](https://stormasm.github.io/mui-tutorial/)**
with the main goal of
using this framework as a test bed for elucidating different aspects of
Material-UI.  So the tutorial and the framework will develop over time
in parallel.  As more interesting aspects of the framework get developed,
the associated documentation teaching the Material-UI concepts will follow.

### The Overall Architecture of the Framework

The concept is simple.  The framework supports views and JSON data.  

The views are any React component that can be accepted inside
[withStyles](https://material-ui.com/customization/css-in-js/#api).
The first example of this is a
[Grid List](https://material-ui.com/demos/grid-list/) with
[Cards](https://material-ui.com/demos/cards/) inside them.

The JSON data comes from any API call or endpoint that returns JSON data.  The API call can be GraphQL, REST, or static JSON data sources such as JSON files sitting on your local disk, your cloud server or inside your Github repo.

### Github World Views

The tutorial repository for *ghw* is called **ghw-drawer** and is
[located here on Github](https://github.com/muitool/ghw-drawer)
or simply click on the Github icon in the upper right hand corner
of the
[AppBar](https://material-ui.com/demos/app-bar/).

Github Worlds (ghw) is a set of views coming from the [Github GraphQL API](https://developer.github.com/v4/).
Using this data visualization framework one can develop new views of data for repositories, users, statistics and anything else that can be derived from this data possibly in concert with other data sets.

The data sets for *ghw* are abstracted away from the underlying visualization so that the only thing needed to display the data is a JSON data file.  Eventually, we might provide a live view of the data coming from the Github GraphQL API; but for now the priority is to only require JSON data sets.  The generation of the JSON data sets is described in another section of the tutorial.  For now, we are providing a test set of JSON data files to better understand the structure of the data along with the program which interprets the data and a sample set of views.

Users are welcome to generate out their own custom views along with the data sets to their liking.

### One repo many views

In the current incarnation of the demo there are four views.

 * view1: vertical scrollable gridlist of cards
 * view2: horizontal single line scrollable gridlist of cards
 * view3: table view with [react-autosuggest](https://github.com/moroshko/react-autosuggest)
 * view4: vertical scrollable gridlist of cards with no avatars

### One view many repos

Each view in the system is accessible via the Views menu.  The repo dropdown
allows one to switch between different Github repositories while staying on the same view.  If you select a different repo the same view will be persistent.

### Data Structure Examples

#### AppBar

At the top of the hierarchy are ways to organize information or
websites.  All websites need to have an
[AppBar](https://material-ui.com/demos/app-bar/).  A nice example
of an AppBar in action is the
[Material-UI Home Page](https://material-ui.com/).
There you will
see the Icon button for drawer open and close.  In the repos
in this tutorial you
will see the same functionality.

#### Gridlists

The Gridlist is used to display a collection of Cards in both
a single horizontal line and with six cards per row.

#### Cards

The cards in this demo contain different data types about
each user that commits to a Github
repository including:
  * the user's name
  * the user's location
  * the user's username
  * a link to the avatar of the user

One can also grab data surrounding stars and forks as well.
