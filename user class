<?php
require "db.php";

class User {
    private $pdo;

    public function __construct() {
        $this->pdo = new DB();
    }
    public function registerUser(String $name, String $email, String $password) {
        $hash = password_hash($password, PASSWORD_DEFAULT);
        $this->pdo->run("INSERT INTO user (naam, email, password) VALUES (:name, :email, :password)",["name"=>$name,"email"=>$email,"password"=>$hash]);        
    }
    public function loginUser($email) {
        return $this->pdo->run("SELECT * FROM user WHERE email = :email", ["email"=>$email])->fetch();
    }
}
