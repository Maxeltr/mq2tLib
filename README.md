mq2tLib is a Java library that contains interfaces for working with the Mq2t plugin system.

Usage
Plugins are loaded using ServiceLoader, which looks for implementations of the interfaces defined in mq2tLib. 
To create a plugin, follow these steps:

1. Implement the necessary interfaces from mq2tLib.
2. Create a file META-INF/services/{fully_qualified_interface_name} and specify the fully qualified name of your plugin class in it.
3. Ensure that your plugin is available in the classpath of your application.

Example of Loading Plugins
ServiceLoader<Mq2tComponent> loader = ServiceLoader.load(Mq2tComponent.class);
for (Mq2tComponent plugin : loader) {
    plugin.start();
}

