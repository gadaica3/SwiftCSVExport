# SwiftCSVExport
Simple way to export csv file with rich feature framework in Swift.

## Features

- Able to give CSV file name.
- Able to set CSV headers using fields.
- Able to convert JSON string into CSV.

First thing is to import the framework. See the Installation instructions on how to add the framework to your project.

```swift
//iOS
import SwiftCSVExport

//macOS
import SwiftCSVExportOSX

```


## Examples:

### Example 1
```swift


// First User Object
let user1:NSMutableDictionary = NSMutableDictionary()
user1.setObject("vignesh", forKey: "name" as NSCopying);
user1.setObject("vigneshuvi@gmail.com", forKey: "email" as NSCopying);

// Secound User Object
let user2:NSMutableDictionary = NSMutableDictionary()
user2.setObject("vinoth", forKey: "name" as NSCopying);
user2.setObject("vinoth@gmail.com", forKey: "email" as NSCopying);

// CSV fields Array
let fields:NSMutableArray = NSMutableArray()
fields.add("name");
fields.add("email");

// CSV rows Array
let data:NSMutableArray  = NSMutableArray()
data.add(user1);
data.add(user2);

let path:String = SwiftCSVExport.exportCSV("userlist",fields: fields,values: data);
print(path)

// Just for fun!!
Output: userlist.csv

name,email
vignesh,vigneshuvi@gmail.com
vinoth,vinoth@gmail.com

```

### Example 2
```swift


// Generate CSV file
let user1:NSMutableDictionary = NSMutableDictionary()
user1.setObject("vignesh", forKey: "name" as NSCopying);
user1.setObject("vigneshuvi@gmail.com", forKey: "email" as NSCopying);

let user2:NSMutableDictionary = NSMutableDictionary()
user2.setObject("vinoth", forKey: "name" as NSCopying);
user2.setObject("vinoth@gmail.com", forKey: "email" as NSCopying);

let data:NSMutableArray  = NSMutableArray()
data.add(user1);
data.add(user2);

let path:String = SwiftCSVExport.exportCSV("userlist",fields: ["name", "email"],values: data);
print(path)

// Just for fun!!
Output: userlist.csv

name,email
vignesh,vigneshuvi@gmail.com
vinoth,vinoth@gmail.com

```

### Example 2
```swift


// Generate CSV file
let user1:NSMutableDictionary = NSMutableDictionary()
user1.setObject("vignesh", forKey: "name" as NSCopying);
user1.setObject("vigneshuvi@gmail.com", forKey: "email" as NSCopying);

let user2:NSMutableDictionary = NSMutableDictionary()
user2.setObject("vinoth", forKey: "name" as NSCopying);
user2.setObject("vinoth@gmail.com", forKey: "email" as NSCopying);

let data:NSMutableArray  = NSMutableArray()
data.add(user1);
data.add(user2);

let path:String = SwiftCSVExport.exportCSV("userlist",fields: ["name", "email"],values: data);
print(path)

// Just for fun!!
Output: userlist.csv

name,email
vignesh,vigneshuvi@gmail.com
vinoth,vinoth@gmail.com

```

### Example 3
```swift

// Able to convert JSON string into CSV.
let string = "[{\"name\":\"vignesh\",\"email\":\"vigneshuvi@gmail.com\"},{\"name\":\"vinoth\",\"email\":\"vinoth@gmail.com\"}]";
let filePath:String = exportCSV("userlist", fields:["name","email"], values:string);
print(filePath)

// Just for fun!!
Output: userlist.csv

name,email
vignesh,vigneshuvi@gmail.com
vinoth,vinoth@gmail.com

```

## Outputs:

That will create a CSV file in the proper directory on both OS X and iOS.

OS X CSV files will be created in the OS X Exports directory (found under: /Library/Exports). The iOS CSV files will be created in your apps document directory under a folder called Exports.

## Configuration

There are a few configurable options in SwiftCSVExport.

```swift

//Set the name of the csv file
CSVExport.export.fileName = "Sample" //default is "csvfile"

//Set the directory in which the csv files will be written
CSVExport.export.directory = "/Library/XXX-folder-name-XXX" //default is the standard exporting directory for each platform.

```

## Installation

### CocoaPods

Check out [Get Started](http://cocoapods.org/) tab on [cocoapods.org](http://cocoapods.org/).

To use SwiftCSVExport in your project add the following 'Podfile' to your project

	source 'https://github.com/CocoaPods/Specs.git'
	platform :ios, '8.0'
	use_frameworks!

	pod 'SwiftCSVExport'

Then run:

    pod install || pod update


## License

SwiftCSVExport is licensed under the MIT License.

## Contact

### Vignesh Kumar
* http://vigneshuvi.github.io