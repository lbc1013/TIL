# 1. Error - can't read property 'map' of undefined.

- When : During the FEC Project, when I implemented overview module's component that displays a main image

- How : I passed the state to the child component from the parent component using react hook. And when I tried to use map function with the state's property(state.currentStyle.photo), I got the error.

- What : The error was 'Cannot read property ‘map’ of undefined.
         (basically saying that state.currentStyle.photo is undefined)

- Solution : I was able to solve this error using the conditional rendering.
</br>
I chose the conditional rendering than inline conditional rendering. This was because I think the conditional rendering has a better readability than the inline conditional rendering when there's complicated conditions.

````javascript
const DefaultView = ({state, updateState, updateMainImage, handleToExpand, handleRightArrow, handleLeftArrow}) => {

  let displayStyleImages, displayMainImage;
  if (state.currentStyle) {
    displayStyleImages =
      <div className='styleImages'>
        {state.currentStyle.photos.map((element, idx) => { //render all style photos
          return <img
            id={idx}
            key={idx}
            className='eachStyleImage'
            onClick={updateMainImage}
            src={element.url}/>;
        })}
      </div>;
    if (state.mainImage === '') {
      displayMainImage = <img id ='main' src ={state.currentStyle.photos[0].url}/>;
    } else {
      displayMainImage = <img id ='main' src ={state.mainImage}/>;
    }
  }

  return (
    <>
      <div className='defaultView'>
        {displayStyleImages}
        <div className='mainImage' id='mainImage'>
          <img onClick={handleLeftArrow} className='btnFloating' id='left' src ='https://img.icons8.com/ios-filled/50/000000/long-arrow-left.png'></img>
          <div onClick={handleToExpand} id='wrap'>
            {displayMainImage}
          </div>
          <img onClick={handleRightArrow} className='btnFloating' id='right' src ='https://img.icons8.com/ios-filled/50/000000/long-arrow-right.png'></img>
        </div>
      </div>
    </>
  );
};
````