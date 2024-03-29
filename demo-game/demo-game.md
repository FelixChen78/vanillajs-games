    This is a demo game to get familar with canvas set up, image sprites, and key events. The game moves player sprite chewbacka up, down, left, or right inside the canvas boundaries.

    HOW TO USE: 
        1. open terminal
        (skip to step 3 if you already cloned the repository)
        2. run git clone https://github.com/FelixChen78/vanillajs-games.git      
        3. cd ../demo-game
        4. run <browser> index.html
            ex. google-chrome index.html 

    CONTROLS:
        ArrowUp, ArrowDown, ArrowLeft, ArrowRight


    DOCUMENTATION:

        CANVAS SETUP:
        // Creates 800 by 500 canvas, sets image smoothing enabled to true and quality to high 

        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = 800;
        canvas.height = 500;
        ctx.imageSmoothingEnabled = true;
        ctx.imageSmoothingQuality = "high";


        GLOBAL VARIABLES:

        @let fps is an {Int} that determines fps limit
        @let fpsInterval is an {Int} that determines frames per second since last count
        @let startTime is an {Int} that determines the new startTime for fps count
        @let now is an {Int} that determines the current time using dateNow() function
        @let then is an {Int} that determines the time left after calculating the difference between now and remainder of elapsed mod fpsInterval
        @let elapsed is an {integer} that determines the time elapsed by calculating the difference between now and then
        @let spriteSheetWidth is an {Int} representing the entire width of the sprite sheet
        @let spriteSheetHeight is an {Int} representing the entire height of the sprite sheet
        @let spriteCol is an {Int} representing the number of columns in the sprite sheet
        @let spriteRow is an {Int} representing the number of rows in the sprite sheet
        @const ground is an {Int} determines the distance from the top of the canvas to where the ground is located
        @const playerSprite is an {object} representing the player image 
        @const background is an {object} representing the background image
        @const player is an {object literal} representing the player in the game
            @variable x is an {Int} representing the top left location x where the player is on the canvas
            @variable y is an {Int} representing the top left location y where the player is on the canvas
            @variable width is an {Int} representing the width of the player sprite
            @variable height is an {Int} representing the height of the player sprite
            @frameX is an {Int} used to determine the row on the player sprite sheet
            @frameY is an {Int} used to determine the column on the player sprite sheet
            @velocity is an {Int} representing the speed at which the player moves


        FUNCTIONS:

        @function drawSprite(img, sX, sY, sW, sH, dX, dY, dW, dH) 
            @purpose draws the playerSprite onto the canvas
            @returns null
            @param img is the source image, player sprite sheet 
            @param sX is the start of top left X location on the source image
            @param sY is the start of top left Y location on the source image
            @param sW is the width or the distance from the start of the X location to the end X location on the source image
            @param sH is the height or the distance from the start of the Y location to the end Y location on the source image
            @param dX is the start of top left X location on the canvas where the source image will be placed
            @param dY is the start of top left Y location on the canvas where the source image will be placed
            @param dW is the width or the distance from the start of the X location to the end of the X location on the canvas where the source image will be placed
            @param dH is the height or the distance from the start of the Y location to the end of the Y location on the canvas where the source image will be placed

        @eventListenerFunction window.addEventListener("keydown", e => {})
            @purpose listens for keydown event
            @returns null
            @param Keydown {String} determines the type of event listener which is keydown
            @param e => {} {function} the function ran when keydown event occurs
                @function e
                    @purpose store true in the array keys at location for ASCII value equal to e.key. Also sets player.moving to true
                    @returns null

        @eventListenerFunction window.addEventListener("keyup", e => {})  
            @purpose listens for keyup event
            @returns null
            @param Keyup {String} determines the type of event listener which is keydown
            @param e => {} {function} the function ran when keydown event occurs
                @function e
                    @purpose delete true in the array keys at location for ASCII value equal to e.key. Also sets player.moving to false
                    @returns null

        @function movePlayer()
            @purpose uses keys array to determine if ArrowUp, ArrowDown, ArrowLeft, or ArrowRight has been pressed. Moves the player at the appropriate direction at the speed of 
                player.speed. It also sets the playerY frame to the appropriate frame on the player sprite sheet
            @returns null
            @param none

        @function handlePlayerFrame()
            @purpose loop through rows in player sprite by incrementing frameX and resetting back to 0
            @return null
            @param none

        @gameLoop(fps)
            @purpose calls the game functions over and over
            @returns null
            @param fps is an {Int} that represents the frame per second limit of the game

        @animate()
            @purpose updates the player sprites
            @returns null
            @param none
