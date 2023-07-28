# EmbeddingProblemRepro
Demonstrates a problem with .NET 8 Preview 6

Having a strange issue with .NET 8 preview 6 and a library that has some views included as "Content". This works perfectly well with .NET 6 and even .NET 8 up to preview 5. Starting with preview 6, the views are no longer embedded, leading to runtime errors in our production app as they cannot be found anymore.

Steps to reproduce:

* clone https://github.com/jbartlau/EmbeddingProblemRepro
* compile a release version with .NET 6 SDK or .NET 8 Preview 5
* the file size is approximately 29 KB (I've added a huge comment to the only view file for clarity reasons)
* enable preview features or update to .NET 8 Preview 6
* compile a release version with this SDK
* file size drops to 8 KB as the view is no longer embedded in the DLL

NB: of course this is a very stripped down version of the real problem, thus the DLL doesn't actually make sense the way it is.
