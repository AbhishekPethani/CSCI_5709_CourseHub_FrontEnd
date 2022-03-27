# Assignment 3 (Frontend)

* *Date Created*: 26 MAR 2022
* *Last Modification Date*: 27 MAR 2022
* *Deployed Web Application URL*: <>
* *Gitlab URL*: <>

## Authors

* [Abhishek Pareshbhai Pethani](ab823206@dal.ca) - *(Maintainer)*

## Getting Started

### Prerequisites

To have a local copy of this assingnment up and running on your local machine, you will first need to install the following software

```
Node JS
```

See the following section for detailed step-by-step instructions on how to install this software 

### Installing

A step by step series of examples that tell you how to get a development env running

```
Step-1: Download Node.js Installer from https://nodejs.org/en/download/
Step-2: Once the installer finishes downloading, launch it and install it.
Step-3: To verify installation, Open a command prompt and enter the command node -v and you should get node version.
Step-4: Download this project. open command prompt and navigate to this project directory.
Step-5: Run the the following commands. The npm install command will download all the dependencies and npm start will create and start deployment server on port 3000 and our application is now accessible on browser.
    npm install
    npm start
step-6: Open any browser and type localhost:3000 
```

## Built With


* [ReactJS](https://reactjs.org/docs/getting-started.html) - The web framework used to develop front end components of this application.
* [React Router](https://v5.reactrouter.com/web/guides/quick-start) - This library is used to handle different navigation routes.
* [Material UI](https://mui.com/getting-started/installation/) - This framework is used to design react components.
* [React Icons](https://mui.com/components/icons/) - This library is used to display star icons for ratings task, and delete icons for delete review task.
* [Axios](https://axios-http.com/docs/intro) - This library is used to make http request(Get, Post, Delete, Put) from web browser to our Node.js backend app.
**

## Sources Used

### react-course.png
The above file is available at [hackr.io](https://hackr.io/blog/react-courses) 
- The file in [hackr.io](https://hackr.io/blog/react-courses) is used to display react course image.
- [hackr.io](https://hackr.io/blog/react-courses)'s file was downloaded and kept inside assets directory under src directory.

### python-course.png
The above file is available at [hackr.io](https://hackr.io/blog/best-python-courses) 
- The file in [hackr.io](https://hackr.io/blog/best-python-courses)  is used to display python course image.
- [hackr.io](https://hackr.io/blog/best-python-courses) 's file was downloaded and kept inside assets directory under src directory.

### java-course.png
The above file is available at [hackr.io](https://hackr.io/blog/best-java-courses) 
- The file in [hackr.io](https://hackr.io/blog/best-java-courses)  is used to display java course image.
- [hackr.io](https://hackr.io/blog/best-java-courses) 's file was downloaded and kept inside assets directory under src directory.

### ml-course.png
The above file is available at [hackr.io](https://hackr.io/blog/machine-learning-courses) 
- The file in [hackr.io](https://hackr.io/blog/machine-learning-courses)  is used to display machine learning course image.
- [hackr.io](https://hackr.io/blog/machine-learning-courses) 's file was downloaded and kept inside assets directory under src directory.

### ai-course.png
The above file is available at [hackr.io](https://hackr.io/blog/artificial-intelligence-courses) 
- The file in [hackr.io](https://hackr.io/blog/artificial-intelligence-courses) is used to display artificial intelligence course image.
- [hackr.io](https://hackr.io/blog/artificial-intelligence-courses)'s file was downloaded and kept inside assets directory under src directory.

### node-course.png
The above file is available at [hackr.io](https://hackr.io/blog/node-js-interview-questions) 
- The file in [hackr.io](https://hackr.io/blog/node-js-interview-questions) is used to display node js course image.
- [hackr.io](https://hackr.io/blog/node-js-interview-questions)'s file was downloaded and kept inside assets directory under src directory.

### ReviewSection.js

*Lines 80 - 82*

```
<Typography variant="h6" component="h2">
    No reviews available for this course.
</Typography>

```

The code above was created by adapting the code in [React Typography component - MUI](https://mui.com/components/typography/) as shown below: 

```
<Typography variant="h1" component="h2">
  h1. Heading
</Typography>;
```

- The code in [React Typography component - MUI](https://mui.com/components/typography/) was implemented by using react-mui library. This library provides various components which is responsive.
- [React Typography component - MUI](https://mui.com/components/typography/)'s Code was used because it provides design and content clearly and efficiently.
- [React Typography component - MUI](https://mui.com/components/typography/)'s Code was modified by changing variant and component props of Typography component. 

### Review.js

*Lines 24 - 73*

```
<Paper sx={{ p: 2, margin: '5px', width: '70%', flexGrow: 1, backgroundColor: (theme) => theme.palette.mode === 'dark' ? '#1A2027' : '#fff', }} >
    <Grid container spacing={2}>
        {/* Display user profile*/}
        <Grid item>
            <ButtonBase sx={{ width: 128, height: 128 }}>
                <Img alt="complex" src={Profile} />
            </ButtonBase>
        </Grid>
        <Grid item xs={12} sm container>
            <Grid item xs container direction="column" spacing={2}>
                <Grid item xs>
                    {/* Display user name*/}
                    <Typography gutterBottom variant="subtitle1" component="div">
                        {review.userName}
                    </Typography>
                    {/* Display review description*/}
                    <Typography variant="body2" gutterBottom>
                        {review.description}
                    </Typography>
                    {/* Display rating given by user*/}
                    <Typography variant="body2" color="text.secondary">
                        {/* map all the star to star icon */}
                        { [...Array(parseInt(review.stars))].map((star, index) => {
                            return (
                                <label>
                                    <FaStar color="#FFC107" size={30}/>
                                </label>
                            )
                        })}
                    </Typography>
                </Grid>
            </Grid>
            {/* If the review is written by current logged in user then display delete icon to delete the review.
                if delete icon is clicked then set this review as review to delete in reviewToDelete state
                and also set isDeleteIconClicked state to true. so, that parent component will perform further action.
            */}
            <Grid item>
                {review.userName ===  currentUser ? <IconButton aria-label="delete" size="large">
                    <DeleteIcon onClick={() => {
                        setReviewToDelete(review)
                        setIsDeleteIconClicked(true)
                    }}  
                    fontSize="inherit"/>
                </IconButton>
                :
                <></>}
            </Grid>
        </Grid>
    </Grid>
</Paper>
```

The code above was created by adapting the code in [React Grid component - MUI](https://mui.com/components/grid/) as shown below: 

```
<Paper
    sx={{
        p: 2,
        margin: 'auto',
        maxWidth: 500,
        flexGrow: 1,
        backgroundColor: (theme) =>
            theme.palette.mode === 'dark' ? '#1A2027' : '#fff',
    }}
>
    <Grid container spacing={2}>
        <Grid item>
            <ButtonBase sx={{ width: 128, height: 128 }}>
                <Img alt="complex" src="/static/images/grid/complex.jpg" />
            </ButtonBase>
        </Grid>
        <Grid item xs={12} sm container>
            <Grid item xs container direction="column" spacing={2}>
                <Grid item xs>
                    <Typography gutterBottom variant="subtitle1" component="div">
                        Standard license
                    </Typography>
                    <Typography variant="body2" gutterBottom>
                        Full resolution 1920x1080 • JPEG
                    </Typography>
                    <Typography variant="body2" color="text.secondary">
                        ID: 1030114
                    </Typography>
                </Grid>
                <Grid item>
                    <Typography sx={{ cursor: 'pointer' }} variant="body2">
                        Remove
                    </Typography>
                </Grid>
            </Grid>
            <Grid item>
                <Typography variant="subtitle1" component="div">
                    $19.00
                </Typography>
            </Grid>
        </Grid>
    </Grid>
</Paper>
```

- The code in [React Grid component - MUI](https://mui.com/components/grid/) was implemented by using react-mui library. This code provides grid layout with multiple material UI components to build complex layout.
- [React Grid component - MUI](https://mui.com/components/grid/)'s Code was used because it provides design that i can use to display review given by user. This complex grid contains Img component that i can directly use to display user's profile. It also contains various Grid component which i can utilise to display user name, review dscription along with given rating and to show delete icon to delete the review.   
- [React Grid component - MUI](https://mui.com/components/grid/)'s Code was modified by adding FaStar icons to display raings, by adding DeleteIcon to only those reviews that the current logged in user has wrote previously. Also, i have passed various props such as, review which contains review details (username, review description, and star ratings), currentUser to display DeleteIcons for reviews written by this current user, setReviewToDelete to set which review to delete when currentUser clicked on DeleteIcons button, and setIsDeleteIconClicked to set isDeleteIconClicked state when current user clicked on DeleteIcons.

### ReviewModal.js

*Lines 35 - 44*

```
const useDidMountEffect = (func, deps) => {
  const didMount = useRef(false);
  useEffect(() => {
    if (didMount.current) {
      func();
    } else {
      didMount.current = true;
    }
  }, deps);
};
```

The code above was created by adapting the code in [How to Make the React useEffect Hook Not Run on Initial Render?](https://thewebdev.info/2021/03/13/how-to-make-the-react-useeffect-hook-not-run-on-initial-render/). This code used as it is.

- [How to Make the React useEffect Hook Not Run on Initial Render?](https://thewebdev.info/2021/03/13/how-to-make-the-react-useeffect-hook-not-run-on-initial-render/)'s Code was used to prevent useEffect hook to run on initial render of ReviewModal component. I have created error handling code which displays errors on ReviewModal when there is change in erros state using useEffect hook. But useEffect hook displays errors on first render (there is no error when ReviewModal component renders for the first time). So in order to disable useEffect hook to display errors on first render, above code is used.  

*Lines 78 - 104*

```
<Modal aria-labelledby="transition-modal-title" aria-describedby="transition-modal-description"
    open={isShow} onClose={() => setIsShow(false)} closeAfterTransition BackdropComponent={Backdrop}
    BackdropProps={{timeout: 500, }} >
    <Fade in={isShow}>
        <Box sx={style}>
            <Typography id="transition-modal-title" variant="h6" component="h2">
                Write a review
            </Typography>
            <Typography>
                <Rating name="simple-controlled" value={stars} size="large" onChange={(event, newValue) => { setStars(newValue); }} />
                {errors.star ? <Typography variant="caption" display="block" gutterBottom> Please select stars! </Typography> : ''}
            </Typography>
            <Typography>
                <TextField value={reviewDescription} 
                    onChange={(event) => {setReviewDescription(event.target.value) }}  
                    fullWidth label="Review" id="fullWidth" />
                {errors.reviewDescription ? <Typography variant="caption" display="block" gutterBottom> Please write a review! </Typography> : ''}
            </Typography>
            {/* call validateReview function on button click */}
            <Typography sx={button}>
                <Button onClick={ () => setErrors(validateReview())} variant="contained">Submit</Button>
            </Typography>
        </Box>
    </Fade>
</Modal>
```

The code above was created by adapting the code in [React Modal component - MUI](https://mui.com/components/modal/) as shown below: 

```
<div>
    <Button onClick={handleOpen}>Open modal</Button>
    <Modal
        aria-labelledby="transition-modal-title"
        aria-describedby="transition-modal-description"
        open={open}
        onClose={handleClose}
        closeAfterTransition
        BackdropComponent={Backdrop}
        BackdropProps={{
          timeout: 500,
        }}
    >
        <Fade in={open}>
            <Box sx={style}>
                <Typography id="transition-modal-title" variant="h6" component="h2">
                Text in a modal
                </Typography>
                <Typography id="transition-modal-description" sx={{ mt: 2 }}>
                Duis mollis, est non commodo luctus, nisi erat porttitor ligula.
                </Typography>
            </Box>
        </Fade>
    </Modal>    
</div>
```

- The code in [React Modal component - MUI](https://mui.com/components/modal/) was implemented by using react-mui library. This code provides modal to display details. When user click on button, this modal will be shown as pop-up.
- [React Modal component - MUI](https://mui.com/components/modal/)'s Code was used because it provides a popover box which gives focused UI so that user can only focus on writing review. Using such design disable interaction with other section and disable scrolling of the page until the modal is open. 
- [React Modal component - MUI](https://mui.com/components/modal/)'s Code was modified by replacing the text inside Typography component with Rating component for star rating, TextField component for review description and Button component to submit the review. I have added error handling functionality to check if the user has selected stars and wrote review in the text field and based on that appropriate errors will be displayed when the user clicked on submit button.

### DeleteReviewDialog.js

*Lines 34 - 47*

```
<Dialog open={isDeleteIconClicked} onClose={() => setIsDeleteIconClicked(false)}
        fullScreen={fullScreen} 
        aria-labelledby="responsive-dialog-title">
    <DialogTitle id="responsive-dialog-title"> {"Are you sure?"} </DialogTitle>
    <DialogContent>
        <DialogContentText>
            By clicking YES will delete your review permanently. 
        </DialogContentText>
    </DialogContent>
    <DialogActions>
        <Button onClick={handleClick} value="Yes">Yes</Button>
        <Button onClick={handleClick} value="No" autoFocus>No</Button>
    </DialogActions>
</Dialog>
```

The code above was created by adapting the code in [React Dialog component - MUI](https://mui.com/components/dialogs/) as shown below: 

```
<Dialog
    fullScreen={fullScreen}
    open={open}
    onClose={handleClose}
    aria-labelledby="responsive-dialog-title"
>
    <DialogTitle id="responsive-dialog-title">
        {"Use Google's location service?"}
    </DialogTitle>
    <DialogContent>
        <DialogContentText>
            Let Google help apps determine location. This means sending anonymous
            location data to Google, even when no apps are running.
        </DialogContentText>
    </DialogContent>
    <DialogActions>
        <Button autoFocus onClick={handleClose}>
            Disagree
        </Button>
        <Button onClick={handleClose} autoFocus>
            Agree
        </Button>
    </DialogActions>
</Dialog>
```

- The code in [React Dialog component - MUI](https://mui.com/components/dialogs/) was implemented by using react-mui library. 
- [React Dialog component - MUI](https://mui.com/components/dialogs/)'s Code was used because it provides Dialogs(a type of modal) to inform users about a task and can contain critical information, require decisions, or involve multiple tasks. Dialogs disable all app functionality when they appear, and remain on screen until user confirmed or dismissed required action.
- [React Dialog component - MUI](https://mui.com/components/dialogs/)'s Code was modified by DialogActions. I have changed buttons in DialogActions and added handleClick function on onClick event. This handleClick function will set which button is clicked. Based on this event, review either will be deleted if user clicked Yes button or remains as it is if user clicked No button. 