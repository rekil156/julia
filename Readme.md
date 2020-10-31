julia    
to open a package manager - ]   
to add a package - add Pluto   
to quit - ctrl+c    

save - use local folder location + filename to save locally   
`/Users/rekilprashanth/Documents/GitHubPersonal/julia/notebooks/`

![Alt text](/img/julia1.png?raw=true "Julia")
![Alt text](/img/pluto1.png?raw=true "Pluto")
![Alt text](/img/ret.png?raw=true "Returning to work")


## Adding a  package in code.
### setting up an empty package environment
```
begin
    import Pkg
    Pkg.activate(mktempdir())
    Pkg.Registry.update()
end
```
### add (ie install) a package to our environment
```
begin
    Pkg.add("Compose")
    # call `using` so that we can use it in our code
    using Compose
end

begin
    Pkg.add("PlutoUI")
    using PlutoUI
end
```
