# CoolClocks


[![Build Status](https://travis-ci.org/malmaud/CoolClocks.jl.svg?branch=master)](https://travis-ci.org/malmaud/CoolClocks.jl)


[![codecov.io](http://codecov.io/github/malmaud/CoolClocks.jl/coverage.svg?branch=master)](http://codecov.io/github/malmaud/CoolClocks.jl?branch=master)

Basics
---
Do all your favorite clock things:

```julia
using CoolClocks
@test 🕟+🕝== 🕔 # 3:30 + 1:30 == 5:00
@test 🕑^50 == 🕓
@test Clock("3:30") == 🕟
let cp = Dates.Hour(3) + Dates.Minute(30)
  @test Clock(cp) == 🕟
  @test Dates.CompoundPeriod(🕟) == cp
end

```

Clock algebra (Clockgebra)
----

```julia
julia> hooks_nightmare = rand(Clock,10,10)
10x10 Array{CoolClocks.Clock,2}:
 🕠  🕢  🕙  🕧  🕦  🕧  🕙  🕘  🕚  🕝
 🕔  🕛  🕔  🕢  🕤  🕥  🕥  🕢  🕦  🕣
 🕓  🕒  🕐  🕝  🕐  🕥  🕘  🕙  🕦  🕕
 🕧  🕒  🕒  🕓  🕟  🕑  🕙  🕗  🕝  🕕
 🕘  🕚  🕟  🕙  🕒  🕞  🕓  🕔  🕥  🕧
 🕓  🕧  🕞  🕞  🕖  🕧  🕐  🕑  🕥  🕝
 🕔  🕣  🕔  🕙  🕠  🕔  🕖  🕞  🕢  🕕
 🕛  🕧  🕥  🕥  🕧  🕚  🕙  🕔  🕛  🕢
 🕕  🕗  🕝  🕧  🕧  🕥  🕕  🕓  🕤  🕘
 🕒  🕓  🕥  🕧  🕣  🕔  🕥  🕘  🕥  🕟
julia> hooks_nightmare * rand(Clock, 10, 2)
10x2 Array{CoolClocks.Clock,2}:
 🕝  🕠
 🕗  🕑
 🕝  🕔
 🕐  🕘
 🕡  🕢
 🕧  🕚
 🕧  🕕
 🕛  🕝
 🕧  🕠
 🕛  🕤
```
