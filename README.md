# StrawberryDonut Story
 
Grammar description of StrawBerry story.
File extension of Strawberry story file is `.donut`

## Grammar

### Scene
Story file is made up of scenes. Scene contains a content, codes, and paths. A scene is declared with `#`. The name of a scene must be a number.
```
#1
```

### Content
Content is surrounded by `"` or `'`. This is a content of a scene. A content must be declared under a scene, and each scene can have only one content. You can also use string format [just like the strawberry language](https://github.com/StrawberryDonut/Strawberry-lang-spec/blob/main/Types.md#string)
```
#1
'Hello, world!'
```

### Code
Code starts with `>` and it is written with [Strawberry Language](https://github.com/StrawberryDonut/Strawberry-lang-spec). The code is executed before or after the content is generated. The moment that the code is executed depends on whether the code declaration is above or below the declaration of the content.   
You can only write single-line codes with '>', but surrounding the code with `{ }` makes you write multi-line codes.
```
#1
'Hello, world!'
> a = 1
> {
    b = 2
    c = a + b
}
```

### Path
With Path, you can add a reaction to the message and can move the scene when the same reaction is added.   
`:<name of emoji>: => #<scene number>` is a basic form of the path. It adds an emoji to the message from Discord's default emojis. And when the user clicks the reaction, The scene is moved.   
You can write an id of your custom emoji insteds of the name of a default emoji.   
You also can skip emoji name just like `=> #3`, It works as same as `:white_check_mark: => #3`. Some of the emojis can be shortened by using `.:<shortcut>:` instead of `:<full name>:`. The shortcut includes: `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `a`, `b`, `c`, `d`, `e`, `f`, `h`, `i`, `j`, `k`, `l`, `m`, `n`, `o`, `p`, `q`, `r`, `s`, `t`, `u`, `v`, `w`, `x`, `y`, `z`   
If you replace `=>` into `->`, the reaction of the emoji won't be added so you can make a secret path with it.   
If there is no path on the scene, that scene will be an ending scene and the story will be stoped.
```
#1
'Hello, world!'
> a = 1
> {
    b = 2
    c = a + b
}
=> #2
:one: => #3
.:c: => #4
:four: -> #5
```
