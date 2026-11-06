<script>
  document.title = "Adam Mathe";
</script>

## Rain Framework

### Rain is a graphics framework I am currently developing without the use of an external math library.

2026 - Present

**Tech:** `C++` `OpenGL` `GLFW`

| ![Image](images/orthographic2.png) | ![Image](images/math.png) |
| :---: | :---|
| *A scene rendered using Rain and its linear algebra library.*| *Some notes I made to understand and derive the orthographic projection matrix.* |

## Motivation Behind the Project

Coming into this project I had a decent amount of experience with C++ and OpenGL, but I relied on GLM for matrix math.

With Rain Framework, my goal is to learn the linear algebra behind graphics programming by deriving and implementing each function by hand.

## Key Features

In the project so far, I have developed a matrix library which includes:
* Matrix multiplication
* Scale matrices
* Translation matrices
* Rotation matrices
* Orthographic projection matrices

<details markdown="1">

<summary><strong>View Example Rendering Loop Code</strong></summary>

> *Example usage code for the framework, initalizes a Rain application and renders a 128x128 textured square.*

```c++
int main()
{
    rain::Application my_game(640, 480, "My Game Name");

    // Shader
    Shader base_program("shaders/base.vert", "shaders/base.frag");

    base_program.use();

    // Create a buffer to pass our vertices to OpenGL
    GLuint vao, vbo, ebo;

    glGenVertexArrays(1, &vao);
    glBindVertexArray(vao);

    glGenBuffers(1, &vbo); // Give 'vbo' a unique ID
    glBindBuffer(GL_ARRAY_BUFFER, vbo); // Tell OpenGL any GL_ARRAY_BUFFER commands pertain to 'vbo'
    glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW); // Give our vertices to OpenGL

    // An Element Array Buffer allows OpenGL to re-use vertices when drawing a primitive
    glGenBuffers(1, &ebo);
    glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, ebo);
    glBufferData(GL_ELEMENT_ARRAY_BUFFER, sizeof(indices), indices, GL_STATIC_DRAW);

    // Load an image and create a texture
    int w, h, channels;
    unsigned char* image_data = stbi_load("assets/magma.png", &w, &h, &channels, 0);

    GLuint texture;
    glGenTextures(1, &texture); // Give 'texture' a unique ID that OpenGL can use to reference it
    glBindTexture(GL_TEXTURE_2D, texture);
    glTexImage2D(GL_TEXTURE_2D, 0, GL_RGBA, w, h, 0, GL_RGBA, GL_UNSIGNED_BYTE, image_data);
    glGenerateMipmap(GL_TEXTURE_2D);

    stbi_image_free(image_data);

    // Matrix tests
    linear::mat4 model = linear::identity();
    linear::mat4 projection = linear::identity();

    linear::scale(model, linear::vec3(128.0, 128.0, 1.0));
    linear::scale(projection, linear::vec3(1 / 320.0, 1 / 240.0, 1.0));

    // Give the matrix to the shader
    base_program.setMat4("model", model);
    base_program.setMat4("projection", projection);

    // Tell OpenGL how to interpret the vertex data
    glEnableVertexAttribArray(0);
    glEnableVertexAttribArray(1);
    glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, 5 * sizeof(float), (void*)0);
    glVertexAttribPointer(1, 2, GL_FLOAT, GL_FALSE, 5 * sizeof(float), (void*)(3 * sizeof(float)));

    // Main window loop
    while(my_game.is_running())
    {
        glClearColor(0.1f, 0.05f, 0.2f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);

        glDrawElements(GL_TRIANGLES, 6, GL_UNSIGNED_INT, 0);

        my_game.present();
    }

    glDisableVertexAttribArray(0);
    glDisableVertexAttribArray(1);

    return 0;
}
```

</details>

## Future Plans

As this project continues, I plan to derive the arbitrary axis rotation matrix and implement the perspective projection matrix. I also plan to extend the linear algebra math library and rendering pipeline to support 3D projects.

## Source Code & Repository

[View Source Code](https://github.com/adam-mathe/rain-framework.git)
