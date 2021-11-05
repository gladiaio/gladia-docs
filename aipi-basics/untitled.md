# Build your first AI APP

## General rule

Creating your first API start with the qualification of the type of problem you are solving.

1. Define your [INPUT type](../master/architecture/input-type.md) (Image / Sound / Text / Video)
2. Define your [OUTPUT type](../master/architecture/output-type.md) (Image / Sound / Text / Video)
3. Define the task you are solving within this INPUT/OUTPUT combination
   1. You can check the list of INPUT / OUTPUT / TASK combinations [here](input-ouput-tasks.md).
   2. you can check existing endpoints [here](broken-reference).
4. There are 2 ways to handle API creation:
   1. Using the build in packages nothing to install but you are not sure 100% of the compatiblity of your API. Still it should be able to handle 95% of use cases
      1. To find if you are compatible you can check the default docker [here](https://github.com/theunifai/unifai-docker). It's based on Kaggle Containers meaning that it should be able to handle most of use cases
      2.  On the other hand it's also possible to build a dedicated environment for your API while remaining in the main framework co-hosted with the rest of the APIs.&#x20;

          1. The framework has been designed to be able to handle custom environments (including custom python versions) based on an environment yaml file.&#x20;
          2. [Here](https://github.com/theunifai/unifai-apis-core/tree/main/src/apis/image/image/super-resolutions/idealo-psnr-small) is an example of an implementation of a custom environment



{% embed url="https://gist.github.com/jqueguiner/2f139d49c4bd6ada480ef52fa1e17924" %}
