<b>STEP 1 : Setting Up</b>
<ul>
<li> Install Visual Studio 2019 with tools and feautures of C#. </li>
<li> Create a new project and select project template as WPF App(.Net Framework)
  <img width="960" alt="image" src="https://user-images.githubusercontent.com/109460490/216130135-4301202c-963a-40c5-b177-7d402a5320cb.png">
</li>
 <li> Enter a name for application and create</li> 
  <li> Go to Project >> Add References >> Search: System Drawing ; Install System Drawing. </li>
  <li> Go to Tools >> NuGet Package Manager >> Manage Packages... >>Search for toolkit ; install Extended WPF Toolkit.</li>
</ul>
<br>
<b> STEP 2 : MainWindow.xaml </b>
 In this we make layout for elements and identufy all the window elements ( radiobutton , textbox etc) we need in our app and location where to place them.
 As we have to make an app for drawing shapes (triangle, rectangle, circle) with custom parameters.
<ul>
  <li>I used two column grid 1:1 in ratio . First column consist of  radiobuttons , labels and textboxes and second half is for drawing shape.
    <img width="245" alt="image" src="https://user-images.githubusercontent.com/109460490/216147383-34bc3174-8919-4c08-8cfe-f79057191f46.png">
</li>
  <li> Make three radiobuttons and name them as ellipse , rectangle , triangle when will click on any radiobutton some function gets execute to set their visibility
  <img width="746" alt="image" src="https://user-images.githubusercontent.com/109460490/216147468-ae5f14eb-451c-4ff8-8e5d-2c6196bfa5d4.png">
  </li>
  <li> Make two textboxes labeled with height and width to get parameters for height, width of the choosen shape.
  <img width="624" alt="image" src="https://user-images.githubusercontent.com/109460490/216147594-1b689fa3-163e-4ba2-b5d3-9c8f57d2d110.png"></li> 
</ul>
<br>
<b> STEP 3: MainWindow.xaml.cs </b>
<ul>
  <li> Create a function ShapeRadios_Click which will execute when will click on any radiobutton , It sets visibility of current selected shape and collapse others.
  <pre><code>private void ShapeRadios_Click(object sender, RoutedEventArgs e)
        {
            RectangleShape.Visibility = Visibility.Collapsed;
            EllipseShape.Visibility = Visibility.Collapsed;
            TriangleShape.Visibility = Visibility.Collapsed;

            switch (((RadioButton)sender).Name)
            {
                case "RectangleRadio":
                    RectangleShape.Visibility = Visibility.Visible;
                    CurrentShape = "Rectangle";
                    break;
                case "EllipseRadio":
                    EllipseShape.Visibility = Visibility.Visible;
                    CurrentShape = "Ellipse";
                    break;
                case "TriangleRadio":
                    TriangleShape.Visibility = Visibility.Visible;
                    CurrentShape = "Triangle";
                    break;
                default:
                    break;
            }
        }</code></pre>
  </li>
  <li> Create a function which will render when we will fill width box. This function sets width of shapes
  <pre><code>private void WidthBox_SelectionChanged(object sender, RoutedEventArgs e)
        {
            double.TryParse(WidthBox.Text, out width);
            RectangleShape.Width = width;
            EllipseShape.Width = width;

            //        100,0
            //          △
            //   0,200     200,200
            PointCollection newpoints = new PointCollection();
            
            newpoints.Add(new System.Windows.Point(0, 0));
            newpoints.Add(new System.Windows.Point(width/2,height));
            newpoints.Add(new System.Windows.Point(width, 0));
            TriangleShape.Points = newpoints;
        }</code></pre></li>
  <li>  Create a function which will render when we will fill height box. This function sets height of shapes
  <pre><code>private void HeightBox_SelectionChanged(object sender, RoutedEventArgs e)
        {
            double.TryParse(HeightBox.Text, out height);
            RectangleShape.Height = height;
            EllipseShape.Height = height;

            
            PointCollection newpoints = new PointCollection();

            
            newpoints.Add(new System.Windows.Point(0, 0));
            newpoints.Add(new System.Windows.Point(width / 2, height));
            newpoints.Add(new System.Windows.Point(width, 0));
            TriangleShape.Points = newpoints;
        }</code></pre></li>
  
</ul>
<b>STEP 4: Testing </b>
<li>Creating rectangle for custom inputs.
<img width="960" alt="image" src="https://user-images.githubusercontent.com/109460490/216140470-00a98fe8-77ce-45d9-b077-b6cf6d4ed6a9.png">
</li>
<li> Creating ellipse for custom inputs
<img width="960" alt="image" src="https://user-images.githubusercontent.com/109460490/216140806-ff902791-b291-4e23-8653-6b8ebc2949b3.png">
</li>
