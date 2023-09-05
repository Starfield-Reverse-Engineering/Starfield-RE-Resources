This folder contains resources for analyzing static libraries compiled into the Starfield binary.

The compiler in use with Starfield is Visual Studio 2019, version 16.11.5 (copy located in tools directory)

Directory structure is like this:

 - \<libname\>
   - \<version_number_1.0.0\>
     - lib - *Built binaries go here*
       - Release - *Release version*
       - RelWithDebInfo - *Release with Debug Info (Make sure to include the pdb generated)*
     - include - *Header files that are installed when using* `cmake install`
     - src - *If the source code is not publicly available, include a tarballed/zip file of the source you compiled here* 
     - README.md - *Specify URL to the source code @ the tagged version and any compiling/build info necessary*
   - \<version_number_2.0.0\>
   - \[etc...\]
   - README.md - Specify here which version is in use with which Starfield version
     - It is unlikely that we will run into multiple versions of a library this early into the RE effort, but this is for future expansion
    
When uploading libraries, make sure to include

- URL to the source code @ the tagged version in the README.md, or include the source code in a tarball/zip if not publicly available.
- The compiled versions of the libraries (*.lib)
  - Compile with vs2019 16.11.5 
  - Include both the Release and RelWithDebInfo versions of the compiled libraries
  - Make sure to include the PDB(s) that come from the RelWithDebInfo 
- All the header files that are installed with `cmake install`
  - if the library does not use cmake, just provide all the header files in the include directory(s)
