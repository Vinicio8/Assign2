#include <iostream>
#include <fstream>
#include <queue>
#include <set>
#include <string>
#include <unordered_set>
std::string kYourName = "Vinicio Guaigua"; 

std::set<std::string> get_applicants(std::string filename) {

  std::set<std::string> applicants;
  std::ifstream file(filename);

  std::string name; 
  while (std::getline(file,name))
  {
    applicants.insert(name);
  }

  file.close();
  return applicants;
  
}

 std::string get_initials(const std::string& name) {
  size_t space_pos = name.find(' ');  
  if (space_pos == std::string::npos) {
      return "";  
      }
  return std::string(1, name[0]) + std::string(1, name[space_pos + 1]);
}


std::queue<const std::string*> find_matches(std::string name, std::set<std::string>& students) {

  std::queue<const std::string*> matches;
  std::string initials = get_initials(name);
  for (const auto& student_name : students)
  {
    if (get_initials(student_name) == initials)
    {
      matches.push(&student_name);
    }
  }
  return matches;
}


std::string get_match(std::queue<const std::string*>& matches) {
 
  if (matches.empty())
  {
    return "No Matches Found!!";
  }
  int random_index = rand() % matches.size();
  std::queue< const std::string*> temp_queue = matches;

  for (int i = 0; i< random_index; i++)
  {
    temp_queue.pop();
  }
  return *temp_queue.front();
}

/* #### Please don't remove this line! #### */
#include "autograder/utils.hpp"
