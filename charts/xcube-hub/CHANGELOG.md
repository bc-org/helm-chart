## Changes in Version 1.0.2

- Version `1.0.1` removed the `initContainers` array from values.yaml as it collided with the prepullContainers 
  array even if empty. Now the template checks the size of both init container arrays and only prints them if not empty. 

## Changes in Version 1.0.1

- Added prepullContainers which adds a container to the deployment that can pre-pull docker images. This improves the user
  experience when docker images get big.