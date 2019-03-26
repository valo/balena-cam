![](./balena-cam/app/client/balena-cam-readme.png)

Live stream your balena device's camera feed.

## Getting started

- Sign up on [balena.io](https://balena.io/) and follow our [Getting Started Guide](https://balena.io/docs/learn/getting-started).
- Clone this repository to your local workspace.
- Set these variables in the `Fleet Configuration` application side tab
  - `BALENA_HOST_CONFIG_start_x` = `1`
  - Set all the following `gpu_mem` variables so your Pi can autoselect how much memory to allocate for hardware accelerated graphics, based on how much RAM it has available

    | Key                                  | Value
    |--------------------------------------|----------
    |**`BALENA_HOST_CONFIG_gpu_mem_256`**  | **`192`**
    |**`BALENA_HOST_CONFIG_gpu_mem_512`**  | **`256`**
    |**`BALENA_HOST_CONFIG_gpu_mem_1024`** | **`448`**

- Using [Balena CLI](https://www.balena.io/docs/reference/cli/), push the code with `balena push <application-name>`.
- See the magic happening, your device is getting updated 🌟Over-The-Air🌟!
- In order for your device to be accessible over the internet, toggle the switch called `PUBLIC DEVICE URL`.
- Once your device finishes updating, you can watch the live feed by visiting your device's public URL.

### Optional Settings

- To rotate the camera feed by 180 degrees, add a **device variable**: `rotation` = `1` (More information about this on the [docs](https://www.balena.io/docs/learn/manage/serv-vars/)).
- To suppress any warnings, add a **device variable**: `PYTHONWARNINGS` = `ignore`

## Additional Information

- This project uses [WebRTC](https://webrtc.org/) (a Real-Time Communication protocol).
- A direct WebRTC connection fails in some cases.
- This current version uses mjpeg streaming when the webRTC connection fails.

## Supported Browsers

- **Chrome**
- **Firefox**
- **Safari**
- **Edge** (only mjpeg stream)

## Installation Note
If your device is a Raspberry Pi One, Zero or ZeroW please use [this](https://github.com/balena-io-playground/balena-cam/tree/pizero-armv6) branch of this project.

## License

Copyright 2018 Balena Ltd.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

<http://www.apache.org/licenses/LICENSE-2.0>

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
