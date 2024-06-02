# What is Metro?

Metro is a Javascript bundler. It converts your project into a single Javascript file. It does this in three phases:

1. **Resolution**
In this step, Metro resolves the reference of a file that is being used in another file, starting from the entry point of the project. This can be a source code file or an asset file. Thus, for each file, Metro resolves the files that are being imported there.
<br>

2. **Transformation**
In this step, Metro converts each of the files into a format which is understandable by the target platform (like React Native). This process usually happens parallely with the resolution step.
<br>

3. **Serialization**
In this step, the converted files are serialized / bundled together to form a single Javascript file.
