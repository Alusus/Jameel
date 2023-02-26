# Jameel
A generic source code beautifier.

## Running and Building

You can run Jameel directly from source, or you can build an executable. Running requires the latest
version of Alusus langauge. At the time of writing you need the latest test build of Alusus; the
0.9.0 version is not recent enough.

Runing directly from source:
```
alusus src/main.alusus [options] <src_file> [<dest_file>]
```

If you run `alusus src/main.alusus` without args you'll get a description of available options.

Building an executable requires GCC to be installed in addition to Alusus. To build an executable:

```
alusus src/main.alusus --build
```

## Adding Rules for a New Language

To add support for a new language you'll need to do the following:

* Build a new rules file. The rules are regex based, and are fairly simple to write. You can look
  at `json_rules.alusus` for a simple example. A more sophisticated example is `alusus_rules.alusus`
  though it's still far simpler than many of the beautifiers out there.

* Update `getLanguageRules` function to include your new language.

* Update the `Available lang options` part of the help.

