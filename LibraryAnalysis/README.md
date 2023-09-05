This folder contains resources for analyzing static libraries compiled into the Starfield binary.

The compiler in use with Starfield is Visual Studio 2019, version 16.11.5 (copy located in tools directory)

Directory structure is like this:

 - libname
   - \<version_number_1.0.0\>
     - lib
     - include
     - src
     - bin *(if applicable)*
   - \<version_number_2.0.0\>
   - \[etc...\]
   - README.md - Specify here which version is in use with which Starfield version
     - It is unlikely that we will run into multiple versions of a library this early into the RE effort, but this is for future expansion
    
When uploading libraries, make sure to include

- URL to the source code @ the tagged version (or upload the source code in a tarball/zip if not publicly available)
- The compiled versions of the libraries (*.lib)
  - Compile with vs2019 16.11.5 
  - Include both the Release and ReleaseWithDebugInfo versions of the compiled libraries
  - Make sure to include the PDB(s) that come from the ReleaseWithDebugInfo 
- All the header files that are installed with `cmake install`
  - if the library does not use cmake, just provide all the header files in the include directory(s)
