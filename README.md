# What's this

This class allows you to **automate the localization** (translation) of your interface (XIB files) **without any additional code in your application**!

To use this, you **only need to add AutoNibL10n.h and .m in your project** and… that's all!

Then in your XIB file, when you use a key of your Localizable.strings in the text of any element
(title of an UIButton, text of a UILabel, …), it will be automatically translated on the fly at runtime.
* You don't need to have one XIB file by language/locale any more!
* You don't need to have an IBOutlet to all of your XIB objects just to translate their text manually!

**All you have to do is use the identifiers/keys that you have declared in your Localizable.string in your XIB.**

***

**BEFORE**, if you wanted to have a single XIB file:

* you needed an "IBOutlet UILabel* myLabel"
* you needed to write some code like "myLabel.text = NSLocalizedString(@"mytext",@"Text of my label");

**NOW**, you just need to:

* set the text of your label to "mytext" directly in InterfaceBuilder in your XIB file
* no need to add an IBOutlet nor write any code!


# How it works

This class uses method swizzling to intercept the calls to awakeFromNib and automatically
localize any objet created/extracted from a XIB file by the runtime. The method swizzling is
done automatically when your application is loaded in memory, so you don't even to add code
to install this: the only presence of the AutoXibL10n.m file in your project make everything magic!

Enjoy!