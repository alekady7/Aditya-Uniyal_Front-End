# SteelEye-Assignment

Q1) Explain what the simple List component does.
Sol: A fundamental building block of React UIs is the `List` component, which accomplishes displaying multiple items via its `<ul>` implementation. 

Two distinct components compose it: `SingleListItem` and `ListComponent`. 

The prior encompasses rendering single elements; however, it requires four properties among them are position used as an "index" and selection status "isSelected." With only one prop named `items`, the `ListComponent` component displays multiple items by providing two key attributes-`onClickHandler` that determines how the item reacts when clicked and accepts an index as input parameter, and `text`, which is simply a string containing information about what that particular item represents. Additionally, this component can render any array whose elements will be displayed in orderly fashion. Maintaining its own local state variable called `selectedIndex`, the `ListComponent` tracks which item is currently selected. This selection tracking occurs through invoking the event handler function, ``handleClick`, whenever an item is clicked. Upon invocation, this function adjusts the value of the  previously mentioned state variable based on what was clicked. Afterwards, it produces updates otehrf components' props with boolean values of whether or not they are equal to said chosen index value, something that signifies if a particular element should stand out as selected or not. To optimize rendering performance, each item in the list is assigned a `key` prop that corresponds to its index.Consequently, in Laymen terms the List component is a simple, reusable component that allows developers to easily display a list of items and keep track of the currently selected item.

Q2) What problems / warnings are there with code?
Sol: a)   The PropTypes.array and PropTypes.shapeOf should be written as PropTypes.arrayOf and PropTypes.shape, respectively. In this line:items: PropTypes.array(PropTypes.shapeOf({
  b) The isSelected prop in the WrappedSingleListItem component is expected to be a boolean value, but it is being passed the selectedIndex state variable, which is a number. This line: isSelected={selectedIndex}
  c) The onClickHandler prop in the WrappedSingleListItem component is being called immediately when the component is rendered, instead of being passed as a function to be called later when the item is clicked. This line:
onClick={onClickHandler(index)}
  d)The setSelectedIndex state setter function is being called instead of selectedIndex in the WrappedListComponent component. This line: const [setSelectedIndex, selectedIndex] = useState();

Q3) The updated ( fix, optimize, and/or modify the component as much as you think is necessary.) Code is in the updated Code repository:
