# Razor Tabs
A Razor Class Library to assist with controlling/displaying tabbed content.

## Overview
* With very little effort, it is easy to build up complex nested controls as seen on this page.
* There are also a number of code samples so you can start building sites yourself!
* The samples project contains a demo of how to use the Razor tab package.


### Default Behaviour:
```
<TabControl>
	<TabItems>
		<TabItem>
			<h5>Here we display the tab contents:</h5>
			<ul class="mb-0">
				<li>This shows the default styling of the tabs control.</li>
				<li>By default, the tabs are labelled with indices if no "Title" is specified.</li>
			</ul>
		</TabItem>
		<TabItem>
			<div class="mt-1">
				This is a second tab item with some more content.
			</div>
		</TabItem>
		<TabItem>
			<div class="mt-1">
				This is a third tab item with even more content.
			</div>
		</TabItem>
	</TabItems>
</TabControl>
```

### Customized Styles:
```
<TabControl>
	<TabHeader>
		<TabHeaderTemplate Class="card-header" ActiveClass="btn-success" InactiveClass="btn-danger" />
	</TabHeader>
	<TabItems>
		<div class="card-body">
			<TabItem Title="Customized 1">
				<h5>Here we display the tab contents:</h5>
				<ul class="mb-0">
					<li>Styles can be applied to the buttons to control how they appear in the page.</li>
					<li>Different styles can be applied to the buttons based on whether they are "Active" or "Inactive".</li>
				</ul>
			</TabItem>
			<TabItem Title="Customized 2">
				<div class="mt-1">
					This is a second tab item with some more content.
				</div>
			</TabItem>
		</div>
	</TabItems>
	<TabFooter>
		<div class="card-footer">
			Static footer content goes here. This content does not change on tab selection.
		</div>
	</TabFooter>
</TabControl>
```

### More advanced features:
RazorTabs also offers more advanced features beyond basic selection including an OnTabSelected EventCallback on the individual Tab Level and one for the whole tab control.
```
<TabControl OnTabSelected="@(() => Console.WriteLine("Hello from the TabControl!"))">
	<TabItems>
		<div class="card-body">
			<TabItem Title="Info">
				<h5>This demonstrates the OnTabSelected functionality for the tab control.</h5>
				<ul class="mb-0">
					<li>EventCallbacks are also provided to support custom logic when any tab, or any specific tab is selected.</li>
					<li>When any tab is selected, the EventCallback on the TabControl is run allowing us to perform additional logic.</li>
					<li>Such events are demonstrated here, whenever any tab is selected, a console message is written saying: "Hello from the TabControl!"</li>
				</ul>
			</TabItem>
			<TabItem Title="Hello World!" OnTabSelected="@(() => Console.WriteLine("Hello World!"))">
				<div class="mt-1">
					Check the console - you should see a log message saying: "Hello World!"
				</div>
			</TabItem>
			<TabItem Title="Goodbye World!" OnTabSelected="@(() => Console.WriteLine("Goodbye World!"))">
				<div class="mt-1">
					Check the console - you should see a log message saying: "Goodbye World!"
				</div>
			</TabItem>
		</div>
	</TabItems>
</TabControl>
```