# H_project_mijaresestrella.html
import React from "react";
import { BrowserRouter as Router, Route, Switch, Link } from "react-router-dom";
import { motion } from "framer-motion";
import { div } from "framer-motion/client";

const Button = ({ children, className, ...props }) => (
  <button className={`px-6 py-3 text-lg rounded-2xl ${className}`} {...props}>
    {children}
  </button>
);

const Card = ({ children, className }) => (
  <div className={`shadow-lg rounded-2xl bg-white p-6 ${className}`}>
    {children}
  </div>
);

const CardContent = ({ children }) => <div className="p-4 flex flex-col items-center">{children}</div>;

const Home = () => (
  <>
    <div className="text-center bg-yellow-50 h-screen flex justify-center items-center">
      <div className="text-center bg-yellow-400 w-screen h-60 mb-32 flex flex-col justify-center items-center">
      <h1 className="text-5xl font-bold text-yellow-600">Fresh Lemons, Pure Quality</h1>
      <p className="text-gray-600 mt-4 max-w-lg text-xl font-mono">Bringing you the finest organic lemons for a healthier life. Experience the zest of nature in every bite.</p>
      <motion.div whileHover={{ scale: 1.1 }} className="mt-6">
        <Link to="/products">
          <Button className="bg-yellow-500 hover:bg-yellow-600 text-white px-6 py-3 text-lg rounded-2xl shadow-md">Explore Products</Button>
        </Link>
      </motion.div>
      </div>
    </div>
  </>
);

const productsData = [
  { name: "Organic Lemons", image: "lemon1.jpg" },
  { name: "Lemon Juice", image: "lemon2.jpg" },
  { name: "Lemon Zest", image: "lemon3.jpg" },
  { name: "Lemon Oil", image: "lemon4.jpg" },
  { name: "Lemon Soap", image: "lemon5.jpg" },
  { name: "Lemon Candy", image: "lemon6.jpg" },
];

const Products = () => (
  <div className="p-10 grid grid-cols-1 md:grid-cols-3 gap-6 bg-yellow-50 min-h-screen">
    {productsData.map((product, index) => (
      <Card key={index} className="shadow-lg rounded-2xl hover:shadow-2xl transition duration-300 flex flex-col">
        <div className="w-full h-80">
          <img src={product.image} alt={product.name} className="w-full h-full object-cover rounded-t-2xl" />
        </div>
        <CardContent>
          <h2 className="text-xl font-semibold text-yellow-700 mt-4">{product.name}</h2>
          <p className="text-gray-500 mt-2">Fresh and natural {product.name.toLowerCase()}.</p>
          <motion.div whileHover={{ scale: 1.1 }} className="mt-4">
            <Button className="bg-yellow-500 hover:bg-yellow-600 text-white px-4 py-2 rounded-xl shadow-md">Buy Now</Button>
          </motion.div>
        </CardContent>
      </Card>
    ))}
  </div>
);

const LemonadeGuide = () => (
  <div className="p-10 bg-gradient-to-b from-yellow-50 to-yellow-100 min-h-screen">
    <h2 className="text-5xl font-bold text-yellow-700 text-center mb-6 drop-shadow-md">🍋 How to Make and Sell Lemonade 🍋</h2>
    <p className="text-center text-gray-600 text-lg max-w-2xl mx-auto mb-8">Learn the secrets of refreshing homemade lemonade and how to turn it into a successful business!</p>
    <div className="mt-8 grid grid-cols-1 md:grid-cols-2 gap-8">
      <Card className="shadow-lg rounded-2xl p-6 bg-yellow-100 flex flex-col items-center text-center transform hover:scale-105 transition duration-300">
        <h3 className="text-3xl font-semibold text-yellow-700 mb-4">🥤 How to Make Lemonade</h3>
        <img src="lemon2.jpg" alt="Making Lemonade" className="w-40 h-40 object-cover rounded-full mb-4 shadow-md" />
        <div className="text-gray-700 text-left w-full">
          <p className="text-lg font-medium text-gray-800 mb-2">Follow these steps to make the perfect lemonade:</p>
          <ol className="list-decimal pl-5 space-y-2 text-lg">
            <li>Squeeze 4 fresh lemons. 🍋</li>
            <li>Mix 1 cup of sugar and 4 cups of water in a pitcher. 💧</li>
            <li>Add lemon juice and stir well. 🌀</li>
            <li>Adjust sweetness as needed. 🍯</li>
            <li>Serve over ice and enjoy! ❄️</li>
          </ol>
        </div>
      </Card>
      <Card className="shadow-lg rounded-2xl p-6 bg-yellow-100 flex flex-col items-center text-center transform hover:scale-105 transition duration-300">
        <h3 className="text-3xl font-semibold text-yellow-700 mb-4">💰 How to Sell Lemonade</h3>
        <img src="lemon-stand.jpg" alt="Lemonade Stand" className="w-40 h-40 object-cover rounded-full mb-4 shadow-md" />
        <div className="text-gray-700 text-left w-full">
          <p className="text-lg font-medium text-gray-800 mb-2">Make your lemonade stand a success:</p>
          <ul className="list-disc pl-5 space-y-2 text-lg">
            <li>Pick a busy spot. 🏙️</li>
            <li>Make an eye-catching sign. 🪧</li>
            <li>Be friendly and smile at customers. 😊</li>
            <li>Offer different flavors or snacks. 🍪</li>
            <li>Keep the price fair and reasonable. 💲</li>
          </ul>
        </div>
      </Card>
    </div>
  </div>
);

const Contact = () => (
  <div className="text-center p-10 bg-yellow-50 min-h-screen flex flex-col items-center">
    <h2 className="text-4xl font-bold text-yellow-600">Contact Us</h2>
    <p className="text-gray-600 mt-4 max-w-md">Have questions? Reach out to us anytime. We'd love to hear from you and help you with anything lemon-related!</p>
    <motion.div whileHover={{ scale: 1.1 }} className="mt-6">
      <Button className="bg-yellow-500 hover:bg-yellow-600 text-white px-6 py-3 text-lg rounded-2xl shadow-md">Email Us</Button>
    </motion.div>
  </div>
);

const Navbar = () => (
  <nav className="bg-yellow-500 p-4 flex justify-between items-center text-white shadow-md">
    <h1 className="text-2xl font-bold">Lemon Bliss</h1>
    <div className="text-sm sm:text-md md:text-xl">
      <Link to="/" className="px-4 hover:text-yellow-200 transition duration-300">Home</Link>
      <Link to="/products" className="px-4 hover:text-yellow-200 transition duration-300">Products</Link>
      <Link to="/lemonade-guide" className="px-4 hover:text-yellow-200 transition duration-300">Lemonade Guide</Link>
      <Link to="/About-us" className="px-4 hover:text-yellow-200 transition duration-300">About Us</Link>
      <Link to="/contact" className="px-4 hover:text-yellow-200 transition duration-300">Contact</Link>
    </div>
  </nav>
);

const AboutLemons = () => {
  return (
    <div className="text-center p-10 bg-yellow-50 min-h-screen flex flex-col items-center">
    <div className="max-w-2xl mx-auto p-6 bg-yellow-100 rounded-2xl shadow-lg text-center">
      <h1 className="text-4xl font-bold text-yellow-600 mb-4">About Us</h1>
      <p className="text-lg text-gray-700 mb-4">
        Welcome to the world of lemons! 🍋
      </p>
      <p className="text-gray-700 mb-4">
        Lemons are more than just a zesty fruit—they’re a symbol of freshness, vitality, and endless possibilities. 
        Whether squeezed into a refreshing drink, used to brighten up a dish, or even as a natural cleaner, 
        lemons have been a beloved part of kitchens and cultures for centuries.
      </p>
      <p className="text-gray-700 mb-4">
        Packed with vitamin C, antioxidants, and a burst of tangy flavor, lemons bring a perfect balance of sour and sweet to life. 
        From lush citrus groves to your table, their journey is one of nature’s simple yet powerful wonders.
      </p>
      <p className="text-gray-700 mb-4">
        At <span className="font-semibold">[Your Brand Name]</span>, we celebrate all things lemon—from their health benefits to their culinary magic. 
        Whether you’re here to learn, explore, or simply appreciate this amazing fruit, we’re here to share the lemon love with you.
      </p>
      <p className="text-lg font-semibold text-yellow-600">When life gives you lemons… enjoy them! 🍋✨</p>
    </div>
    <motion.div whileHover={{ scale: 1.1 }} className="mt-6">
    </motion.div>
  </div>
  );
};

const App = () => {
  return (
    <Router>
      <Navbar />
      <Switch>
          <Route exact path="/" component={Home} />
          <Route path="/products" component={Products} />
          <Route path="/lemonade-guide" component={LemonadeGuide} />
          <Route path="/About-us" component={AboutLemons} />
          <Route path="/contact" component={Contact} />
      </Switch>
    </Router>
  );
};

export default App;
