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
## Lesson1  
* adding packages 
```
begin
    import Pkg
    Pkg.activate(mktempdir())
end

begin
    Pkg.add(["Images", "ImageIO", "ImageMagick"])
    using Images
end
```
* writing multiple statements in a `begin-end` block 
`a = begin b =1; c=4; b+c end`
* typeof(image)
* size(image)
* reverse(image, dims =2)

* img_copy = copy(image)
* **BROADCASTING** 
```
begin 
    new_img = copy(old_img)
    new_img[100:200, 1:100] .= RGB(0, 1, 0)
    new_img
end
```
* **BROADCASTING FUNCTION**
```
# define a function that turns a colour into just its red component
function redify(color)
    return RGB(color.r, 0, 0)
end

redify.(image)
```
* Adding UI element 
```
begin
    Pkg.add("PlutoUI")
    using PlutoUI
end 
```
adding a slider   
```
@bind deciamte_ratio Slider(1:10, show_value=true)
decimate(img,deciamte_ratio)
```

