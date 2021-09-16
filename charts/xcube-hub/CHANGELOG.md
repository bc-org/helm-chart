## Changes in Version 1.0.4

- Added a delay parameter to teh readiness probe of xcube-hub. Can be helpful on e.g. minikube if starting up xcube-hub takes too long
- Allowed to switch off readiness and liveness probes for xcube-hub

## Changes in Version 1.0.3

- Added comments to values.yaml for better understanding

## Changes in Version 1.0.2

- Version `1.0.1` removed the `initContainers` array from values.yaml as it collided with the prepullContainers 
  array even if empty. Now the template checks the size of both init container arrays and only prints them if not empty. 

## Changes in Version 1.0.1

- Added prepullContainers which adds a container to the deployment that can pre-pull docker images. This improves the user
  experience when docker images get big.