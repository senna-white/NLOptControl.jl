# NLOptControl.jl

[![Build Status](https://ci.appveyor.com/api/projects/status/f480ahs29c85m6ne?svg=true)](https://ci.appveyor.com/project/huckl3b3rry87/nloptcontrol-jl)
[![travis](https://travis-ci.org/JuliaMPC/NLOptControl.jl.svg?branch=master)](https://travis-ci.org/JuliaMPC/NLOptControl.jl)

This software solves **nonlinear control problems** at a **high-level** very **quickly**.

Adds to [juliaOpt](http://www.juliaopt.org/) community by:

* Providing an implementation of direct-collocation methods for solving optimal control problems in julia
* Solving nonlinear optimal control problems at a high-level
* Visualizing the solution

## Documentation

[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://juliampc.github.io/NLOptControl.jl/stable/)
[![Latest](https://img.shields.io/badge/docs-latest-blue.svg)](https://juliampc.github.io/NLOptControl.jl/latest/)

## Installation

If you are using **Linux** make sure that you have **gfortran** to run **Ipopt**:

```bash
sudo apt-get update
sudo apt-get install gfortran
sudo apt-get install liblapack-dev  # 线代的包
sudo apt-get install libblas-dev
```

Also, make sure that you are using at least julia 1.0.0  # 安装了1.8.0，在download路径下，下载链接：https://julialang.org/downloads/ 使用教程：http://www.juliaopt.org/packages/

Then open up julia and install NLOptControl

```julia
import Pkg # using Pkg # refer_to https://github.com/jump-dev/Ipopt.jl added in 20220420
Pkg.add("https://github.com/JuliaMPC/NLOptControl.jl")
Pkg.pin("KNITRO",v"0.4")  # 无法使用 pin；解决方法参照：https://github.com/jump-dev/KNITRO.jl/issues/184；https://www.artelys.com/docs/knitro//3_referenceManual/knitroJuliareference.html；结果需要许可证下载安装一个软件，https://www.artelys.com/fr/espace-client/telecharger-knitro/；赋予环境变量； remove KNITRO 删除安装不完整的包；继续尝试：https://discourse.julialang.org/t/error-methoderror-no-method-matching-pin-string-versionnumber/19672，结果： Pkg.add(PackageSpec(name="KNITRO",version="0.4"))无法安装，Pkg.add(PackageSpec(name="KNITRO"))安装了个0.12.0版本的(使用前using Pkg);
Pkg.clone("https://github.com/JuliaMPC/NLOptControl.jl") # https://discourse.julialang.org/t/pkg-clone-command-not-being-recognized/63391/2; clone已无法使用，使用add，url
```

## Citation

If you find [NLOptControl.jl](https://github.com/JuliaMPC/NLOptControl.jl) useful, please cite it:

```LaTeX
@software{nlopt,
  author = {{Huckleberry Febbo}},
  title = {NLOptControl.jl},
  url = {https://github.com/JuliaMPC/NLOptControl.jl},
  version = {0.0.1},
  date = {2017-06-17},
}
```

## Acknowledgements

* [JuMP.jl](https://jump.readthedocs.io/en/latest/) is an important part of this NLOptControl.jl and discussions with Miles Lubin where helpful
* Chris Rackauckas is a very helpful member of the julia community and has provided me support and advice multiple times his software [DifferentialEquations.jl](https://github.com/JuliaDiffEq/DifferentialEquations.jl) is also part of NLOptControl.jl
