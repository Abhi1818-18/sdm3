CREATE TABLE Users (
  user_id INT PRIMARY KEY AUTO_INCREMENT,
  username VARCHAR(50) NOT NULL,
  password VARCHAR(100) NOT NULL,
  email VARCHAR(100) NOT NULL,
  role ENUM('Farmer', 'Agricultural Expert', 'Administrator') NOT NULL
);

-- Table: Crops
CREATE TABLE Crops (
  crop_id INT PRIMARY KEY AUTO_INCREMENT,
  crop_name VARCHAR(100) NOT NULL,
  crop_type VARCHAR(50) NOT NULL,
  description TEXT,
  -- Additional crop attributes
  -- ...
);

-- Table: Farmers
CREATE TABLE Farmers (
  farmer_id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT NOT NULL,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL,
  contact_number VARCHAR(20)
);
address VARCHAR(100),
  -- Additional farmer attributes
  -- ...
  FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

-- Table: Experts
CREATE TABLE Experts (
  expert_id INT PRIMARY KEY AUTO_INCREMENT,
  user_id INT NOT NULL,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL,
  contact_number VARCHAR(20),
  expertise_area VARCHAR(100),
  -- Additional expert attributes
  -- ...
  FOREIGN KEY (user_id) REFERENCES Users(user_id)
);
