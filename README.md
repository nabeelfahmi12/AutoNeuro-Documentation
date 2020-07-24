<<<<<<< HEAD
# Sample_Auto
=======
<div align="center">
  <img src="https://2s7gjr373w3x22jf92z99mgm5w-wpengine.netdna-ssl.com/wp-content/uploads/2020/02/Qeexo_auto_ML.png">
</div>
<h1> AutoNeuro</h1>

[![Python](https://img.shields.io/pypi/pyversions/tensorflow.svg?style=plastic)](https://badge.fury.io/py/tensorflow)
[![PyPI](https://badge.fury.io/py/tensorflow.svg)](https://badge.fury.io/py/tensorflow)

**`Documentation`** |
------------------- |
[![Documentation](https://img.shields.io/badge/api-reference-blue.svg)](https://jhansi-27.github.io/Sample_Auto/) |

AutoNeuro is an automated machine learning app, which allows users to build production ready ML models with ease and efficiency.
The user will only give dataset in recognizable formats and select the type of problem, and the result will be the best performing hyper tuned machine learning model.
The descriptive and graphical analysis of the data are also displayed. The user will also get privileges to choose the deployment option. 

## Install

See the [AutoNeuro install guide](https://www.tensorflow.org/install) for the
[pip package](https://www.tensorflow.org/install/pip), to
[enable GPU support](https://www.tensorflow.org/install/gpu), use a
[Docker container](https://www.tensorflow.org/install/docker), and
[build from source](https://www.tensorflow.org/install/source).

To install the current release, which includes support for
[CUDA-enabled GPU cards](https://www.tensorflow.org/install/gpu) *(Ubuntu and
Windows)*:

```
$ pip install autoneuro

```

A smaller CPU-only package is also available:

```
$ pip install autoneuro-cpu
```

To update TensorFlow to the latest version, add `--upgrade` flag to the above
commands.

*Nightly binaries are available for testing using the
[tf-nightly](https://pypi.python.org/pypi/tf-nightly) and
[tf-nightly-cpu](https://pypi.python.org/pypi/tf-nightly-cpu) packages on PyPi.*
#### 

```shell
$ python
```

```python
>>> import autoneuro as an
>>> an.add(1, 2).numpy()
3
>>> hello = an.constant('Hello, AutoNeuro!')
>>> hello.numpy()
b'Hello, AutoNeuro!'
```

For more examples, see the
[AutoNeuro tutorials](https://www.tensorflow.org/tutorials/).

## Contribution guidelines

**If you want to contribute to TensorFlow, be sure to review the
[contribution guidelines](CONTRIBUTING.md). This project adheres to TensorFlow's
[code of conduct](CODE_OF_CONDUCT.md). By participating, you are expected to
uphold this code.**

**We use [GitHub issues](https://github.com/tensorflow/tensorflow/issues) for
tracking requests and bugs, please see
[AutoNeuro Discuss](https://groups.google.com/a/tensorflow.org/forum/#!forum/discuss)
for general questions and discussion, and please direct specific questions to
[Stack Overflow](https://stackoverflow.com/questions/tagged/tensorflow).**

The AutoNeuro project strives to abide by generally accepted best practices in
open-source software development:

[![Fuzzing Status](https://oss-fuzz-build-logs.storage.googleapis.com/badges/tensorflow.svg)](https://bugs.chromium.org/p/oss-fuzz/issues/list?sort=-opened&can=1&q=proj:tensorflow)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/1486/badge)](https://bestpractices.coreinfrastructure.org/projects/1486)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v1.4%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

## Continuous build status

### Official Builds

Build Type               | Status                                                                                                                                                                           | Artifacts
------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------
**Linux CPU**            | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-cc.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-cc.html)           | [PyPI](https://pypi.org/project/tf-nightly/)
**Linux GPU**            | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-gpu-py3.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-gpu-py3.html) | [PyPI](https://pypi.org/project/tf-nightly-gpu/)
**Linux XLA**            | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-xla.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/ubuntu-xla.html)         | TBA
**macOS**                | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/macos-py2-cc.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/macos-py2-cc.html)     | [PyPI](https://pypi.org/project/tf-nightly/)
**Windows CPU**          | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/windows-cpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/windows-cpu.html)       | [PyPI](https://pypi.org/project/tf-nightly/)
**Windows GPU**          | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/windows-gpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/windows-gpu.html)       | [PyPI](https://pypi.org/project/tf-nightly-gpu/)
**Android**              | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/android.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/android.html)               | [![Download](https://api.bintray.com/packages/google/tensorflow/tensorflow/images/download.svg)](https://bintray.com/google/tensorflow/tensorflow/_latestVersion)
**Raspberry Pi 0 and 1** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/rpi01-py3.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/rpi01-py3.html)           | [Py3](https://storage.googleapis.com/tensorflow-nightly/tensorflow-1.10.0-cp34-none-linux_armv6l.whl)
**Raspberry Pi 2 and 3** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/rpi23-py3.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/rpi23-py3.html)           | [Py3](https://storage.googleapis.com/tensorflow-nightly/tensorflow-1.10.0-cp34-none-linux_armv7l.whl)
**Libtensorflow MacOS CPU** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-mac-cpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-mac-cpu.html)           | [GCS](https://storage.googleapis.com/libtensorflow-nightly)
**Libtensorflow Linux CPU** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-linux-cpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-linux-cpu.html)           | [GCS](https://storage.googleapis.com/libtensorflow-nightly)
**Libtensorflow Linux GPU** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-linux-gpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-linux-gpu.html)           | [GCS](https://storage.googleapis.com/libtensorflow-nightly)
**Libtensorflow Windows CPU** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-win-cpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-win-cpu.html)           | [GCS](https://storage.googleapis.com/libtensorflow-nightly)
**Libtensorflow Windows GPU** | [![Status](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-win-gpu.svg)](https://storage.googleapis.com/tensorflow-kokoro-build-badges/libtensorflow-win-gpu.html)           | [GCS](https://storage.googleapis.com/libtensorflow-nightly)


### Community Supported Builds

Build Type                                                                          | Status                                                                                                                                                                                        | Artifacts
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------
**Linux AMD ROCm GPU** Nightly                                                      | [![Build Status](http://ml-ci.amd.com:21096/job/tensorflow-rocm-nightly/badge/icon)](http://ml-ci.amd.com:21096/job/tensorflow-rocm-nightly)                                                  | [Nightly](http://ml-ci.amd.com:21096/job/tensorflow-rocm-nightly/lastSuccessfulBuild/)
**Linux AMD ROCm GPU** Stable Release                                               | [![Build Status](http://ml-ci.amd.com:21096/job/tensorflow-rocm-release/badge/icon)](http://ml-ci.amd.com:21096/job/tensorflow-rocm-release/)                                                 | Release [1.15](http://ml-ci.amd.com:21096/job/tensorflow-rocm-release/lastSuccessfulBuild/) / [2.x](http://ml-ci.amd.com:21096/job/tensorflow-rocm-v2-release/lastSuccessfulBuild/)
**Linux s390x** Nightly                                                             | [![Build Status](http://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_CI/badge/icon)](http://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_CI/)                                                             | [Nightly](http://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_CI/)
**Linux s390x CPU** Stable Release                                                  | [![Build Status](http://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_Release_Build/badge/icon)](https://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_Release_Build/)                                      | [Release](https://ibmz-ci.osuosl.org/job/TensorFlow_IBMZ_Release_Build/)
**Linux ppc64le CPU** Nightly                                                       | [![Build Status](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Build/badge/icon)](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Build/)                                       | [Nightly](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Nightly_Artifact/)
**Linux ppc64le CPU** Stable Release                                                | [![Build Status](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Release_Build/badge/icon)](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Release_Build/)                       | Release [1.15](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_CPU_Release_Build/) / [2.x](https://powerci.osuosl.org/job/TensorFlow2_PPC64LE_CPU_Release_Build/)
**Linux ppc64le GPU** Nightly                                                       | [![Build Status](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Build/badge/icon)](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Build/)                                       | [Nightly](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Nightly_Artifact/)
**Linux ppc64le GPU** Stable Release                                                | [![Build Status](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Release_Build/badge/icon)](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Release_Build/)                       | Release [1.15](https://powerci.osuosl.org/job/TensorFlow_PPC64LE_GPU_Release_Build/) / [2.x](https://powerci.osuosl.org/job/TensorFlow2_PPC64LE_GPU_Release_Build/)
**Linux aarch64 CPU** Nightly <br> Python 3.6                                       | [![Build Status](http://openlabtesting.org:15000/badge?project=tensorflow%2Ftensorflow)](https://status.openlabtesting.org/builds/builds?project=tensorflow%2Ftensorflow)                     | [Nightly](https://status.openlabtesting.org/builds/builds?project=tensorflow%2Ftensorflow&job_name=tensorflow-arm64-build-daily-master)
**Linux CPU with Intel oneAPI Deep Neural Network Library (oneDNN)** Nightly        | [![Build Status](https://tensorflow-ci.intel.com/job/tensorflow-mkl-build-whl-nightly/badge/icon)](https://tensorflow-ci.intel.com/job/tensorflow-mkl-build-whl-nightly/)                     | [Nightly](https://tensorflow-ci.intel.com/job/tensorflow-mkl-build-whl-nightly/)
**Linux CPU with Intel oneAPI Deep Neural Network Library (oneDNN)** Stable Release | ![Build Status](https://tensorflow-ci.intel.com/job/tensorflow-mkl-build-release-whl/badge/icon)                                                                                              | Release [1.15](https://pypi.org/project/intel-tensorflow/1.15.0/) / [2.x](https://pypi.org/project/intel-tensorflow/)
**Red Hat® Enterprise Linux® 7.6 CPU & GPU** <br> Python 2.7, 3.6                   | [![Build Status](https://jenkins-tensorflow.apps.ci.centos.org/buildStatus/icon?job=tensorflow-rhel7-3.6&build=2)](https://jenkins-tensorflow.apps.ci.centos.org/job/tensorflow-rhel7-3.6/2/) | [1.13.1 PyPI](https://tensorflow.pypi.thoth-station.ninja/index/)

## Resources

*   
*   


Learn more about the
[AutoNeuro community](https://www.tensorflow.org/community) and how to
[contribute](https://www.tensorflow.org/community/contribute).

## License

[AutoNeuro License 2.0](LICENSE)
>>>>>>> origin/gh-pages


neww