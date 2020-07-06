When using the DevExtreme framework for building an application, you can define actions in an abstract way - via [commands](/Documentation/17_2/Guide/SPA_Framework/Views_and_Layouts/#Add_Commands_to_Views). While specifying the action to be performed, you do not create a widget that will be displayed in a UI to provide the specified action. The widget representing a command will be then created automatically by the framework according to [command mapping](/api-reference/40%20SPA%20Framework/HtmlApplication/1%20Configuration/commandMapping.md '/Documentation/ApiReference/SPA_Framework/HtmlApplication/Configuration/#commandMapping') that you specify for the application. Although, you can set an icon for a command as well. For this purpose, the [dxCommand](/api-reference/40%20SPA%20Framework/Markup%20Components/dxCommand/1%20Configuration '/Documentation/ApiReference/SPA_Framework/Markup_Components/dxCommand/Configuration/') component defining a command exposes the **icon** configuration option. This is the option that can be used to set an icon from the Icon Library.

    <!--HTML--><div data-options="dxView: { name: 'index', title: 'Home' }">
		<div data-bind="dxCommand: { id: 'myCommand', onExecute: '#product-details', title: 'Add', icon: 'add' } "></div>
	</div>