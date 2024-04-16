# APIs
**April 16, 2024**

## Introduction
If you call `print()`, the operating system prints the text you give it to the console. Likewise, calling `openFile()` also asks the operating system to perform a task for you. Both of these functions are contained within the computer you are on.

Now, what if you wanted to find the weather at your location?
You could ask the operating system where you're located, but your operating system won't be able to give you weather predictions, because your device doesn't have the sensors for that.

Instead, you can ask a weather service for that data, much like you ask the operating system to open a file, e.g.:
```python
getCurrentWeather("Toronto, Ontario, Canada")
```
This behaviour is provided by an *API*, or *Application Programming Interface*.

## API Components
### Protocols
The method that an API and a program will use to communicate.
*JSON* is a very common file format used to send data to and from Web APIs.

### Security
APIs cost money to run—for example, a local weather service will want to be compensated for their efforts so they can pay their employees and maintain their servers.

APIs will typically restrict access to programs that have a valid *API key* (a code given to you by the developer of the API). Programs send an API key along with any requests to the API, and the API key is checked for validity before the request is processed.

This also makes it easy to restrict access to malicious users:
* The developer can avoid giving them an API key in the first place.
* Any API keys they obtain can be revoked.

### Versions
Several versions of an API may be hosted at the same time to allow for backwards compatibility.

## REST & GraphQL
* REST gives you *whatever data the website wants to give you*.
* GraphQL allows you to specify exactly what data you want back (and is more efficient as a result).