# Discord Bot Document Database Schema Design

*Optimized for MongoDB/Document Store with Crystal Integration*

---

## Collection Overview

This schema is designed for document databases like MongoDB, taking advantage of embedded documents and flexible schema structures. The design supports both students and staff with role-based access and comprehensive progress tracking.

---

## 📚 Users Collection

**Collection Name**: `users`

### Student User Document Example

```json
{
  "_id": ObjectId("..."),
  "discord_id": "123456789012345678",
  "user_type": "student",
  "created_at": ISODate("2025-01-15T10:30:00Z"),
  "updated_at": ISODate("2025-01-20T14:25:00Z"),
  "is_active": true,
  
  "student_data": {
    "progress_level": 5,
    "total_exp": 1250,
    "current_exp": 150,
    
    "scores": [
      {
        "assessment_id": "assessment_001",
        "assessment_name": "Basic Crystal Syntax",
        "score": 85,
        "max_score": 100,
        "percentage": 85.0,
        "attempts": 2,
        "completed_at": ISODate("2025-01-18T09:15:00Z"),
        "metadata": {
          "time_taken_minutes": 25,
          "hints_used": 1,
          "difficulty_rating": "intermediate"
        }
      }
    ],
    
    "quests": [
      {
        "quest_id": "quest_001",
        "quest_name": "First Steps",
        "status": "completed",
        "exp_gained": 100,
        "started_at": ISODate("2025-01-15T10:30:00Z"),
        "completed_at": ISODate("2025-01-15T11:45:00Z"),
        "progress_data": {
          "steps_completed": ["install_crystal", "hello_world", "first_compile"],
          "current_step": null,
          "notes": "Completed quickly with minimal help"
        }
      }
    ],
    
    "assessments_required": [
      {
        "assessment_id": "assessment_003",
        "assessment_name": "Advanced Crystal OOP",
        "status": "required",
        "required_level": 6,
        "assigned_at": ISODate("2025-01-20T09:00:00Z"),
        "due_date": ISODate("2025-01-27T23:59:59Z"),
        "attempts_remaining": 3,
        "priority": "high"
      }
    ],
    
    "badges": [
      {
        "badge_id": "badge_001",
        "badge_name": "Quick Learner",
        "badge_description": "Complete first quest in under 2 hours",
        "badge_icon_url": "https://cdn.example.com/badges/quick_learner.png",
        "earned_at": ISODate("2025-01-15T11:45:00Z"),
        "criteria_met": {
          "quest_completed": "quest_001",
          "time_requirement": "under_2_hours",
          "completion_time_minutes": 75
        },
        "is_visible": true,
        "rarity": "common"
      }
    ]
  }
}
```

### Staff User Document Example

```json
{
  "_id": ObjectId("..."),
  "discord_id": "987654321098765432",
  "user_type": "staff",
  "created_at": ISODate("2025-01-01T00:00:00Z"),
  "updated_at": ISODate("2025-01-20T14:25:00Z"),
  "is_active": true,
  
  "staff_data": {
    "roles": [
      {
        "role_name": "instructor",
        "permissions": {
          "can_create_assessments": true,
          "can_grade_assessments": true,
          "can_create_quests": true,
          "can_view_all_students": true,
          "can_modify_student_progress": true,
          "can_access_admin_dashboard": true,
          "assessment_level_access": [1, 2, 3, 4, 5]
        },
        "assigned_at": ISODate("2025-01-01T00:00:00Z"),
        "assigned_by": "admin_discord_id_here",
        "is_active": true
      }
    ],
    "department": "Computer Science",
    "specializations": ["Crystal Programming", "Database Design", "Web Development"]
  }
}
```

---

## 📋 Assessments Collection

**Collection Name**: `assessments`

```json
{
  "_id": ObjectId("..."),
  "assessment_id": "assessment_001",
  "assessment_name": "Basic Crystal Syntax",
  "assessment_level": 3,
  "difficulty": "intermediate",
  "category": "programming_fundamentals",
  
  "question": {
    "prompt": "Create a Crystal program that demonstrates proper class inheritance",
    "instructions": [
      "Create a base class called 'Animal' with name and age properties",
      "Create a derived class 'Dog' that inherits from Animal",
      "Add a bark method to the Dog class",
      "Instantiate both classes and call their methods"
    ],
    "starter_code": "# Write your Crystal code here\n",
    "hints": [
      "Remember to use the 'class' keyword",
      "Use 'initialize' for constructors",
      "Inheritance uses the '<' symbol"
    ]
  },
  
  "expected_output": {
    "description": "Working Crystal program with inheritance",
    "sample_output": "Animal: Buddy, Age: 3\nWoof! Woof!",
    "evaluation_criteria": [
      {
        "criterion": "correct_syntax",
        "points": 30,
        "description": "Code compiles without errors"
      },
      {
        "criterion": "inheritance_implemented", 
        "points": 40,
        "description": "Proper class inheritance structure"
      },
      {
        "criterion": "methods_work",
        "points": 30,
        "description": "All methods function as expected"
      }
    ]
  },
  
  "scoring": {
    "max_score": 100,
    "passing_score": 70,
    "time_limit_minutes": 45,
    "max_attempts": 3,
    "auto_grade": false
  },
  
  "prerequisites": {
    "required_level": 3,
    "required_assessments": ["assessment_basic_syntax"],
    "required_quests": ["quest_crystal_basics"]
  },
  
  "metadata": {
    "created_by": "instructor_discord_id",
    "created_at": ISODate("2025-01-10T09:00:00Z"),
    "updated_at": ISODate("2025-01-15T14:30:00Z"),
    "is_active": true,
    "tags": ["crystal", "oop", "inheritance", "beginner-friendly"],
    "estimated_duration_minutes": 30
  }
}
```

---

## 🎯 Quests Collection

**Collection Name**: `quests`

```json
{
  "_id": ObjectId("..."),
  "quest_id": "quest_001",
  "quest_name": "Crystal Installation Master",
  "quest_type": "tutorial",
  
  "description": "Learn to install and set up Crystal programming language on your system",
  
  "tasks": [
    {
      "task_id": "install_crystal",
      "title": "Install Crystal",
      "description": "Follow the installation guide for your operating system",
      "points": 30,
      "verification": {
        "type": "command_output",
        "command": "crystal --version",
        "expected_pattern": "Crystal \\d+\\.\\d+\\.\\d+"
      }
    },
    {
      "task_id": "hello_world", 
      "title": "Create Hello World",
      "description": "Write and run your first Crystal program",
      "points": 40,
      "verification": {
        "type": "code_submission",
        "expected_output": "Hello, World!"
      }
    },
    {
      "task_id": "first_compile",
      "title": "Compile Your Program", 
      "description": "Compile your Crystal program to an executable",
      "points": 30,
      "verification": {
        "type": "file_exists",
        "file_pattern": "hello*"
      }
    }
  ],
  
  "rewards": {
    "exp_reward": 100,
    "bonus_exp": 25,
    "badges": ["first_quest_complete"],
    "unlocks": ["quest_002", "assessment_basic_syntax"]
  },
  
  "requirements": {
    "required_level": 1,
    "prerequisites": {
      "quests": [],
      "assessments": [],
      "badges": []
    },
    "estimated_time_minutes": 90,
    "difficulty": "beginner"
  },
  
  "metadata": {
    "created_by": "system",
    "created_at": ISODate("2025-01-01T00:00:00Z"),
    "updated_at": ISODate("2025-01-01T00:00:00Z"),
    "is_active": true,
    "category": "setup",
    "tags": ["installation", "setup", "beginner", "required"]
  }
}
```

---

## 🚀 Database Indexes

### Performance Optimization Indexes

```javascript
// Users Collection Indexes
db.users.createIndex({ "discord_id": 1 })  // Primary lookup
db.users.createIndex({ "user_type": 1 })
db.users.createIndex({ "student_data.progress_level": 1 })
db.users.createIndex({ "student_data.assessments_required.status": 1 })

// Assessments Collection Indexes  
db.assessments.createIndex({ "assessment_id": 1 })
db.assessments.createIndex({ "assessment_level": 1 })
db.assessments.createIndex({ "difficulty": 1 })
db.assessments.createIndex({ "metadata.is_active": 1 })

// Quests Collection Indexes
db.quests.createIndex({ "quest_id": 1 })
db.quests.createIndex({ "quest_type": 1 })
db.quests.createIndex({ "requirements.required_level": 1 })
db.quests.createIndex({ "metadata.is_active": 1 })
```

---

## 💎 Crystal Integration Examples

### Basic User Operations

```crystal
# Check if user exists (new user detection)
def is_new_user?(discord_id : String) : Bool
  DatabaseService.count("users", {"discord_id" => discord_id}) == 0
end

# Get complete user document
def get_user(discord_id : String)
  DatabaseService.find_one("users", {"discord_id" => discord_id})
end

# Create new student user
def create_student_user(discord_id : String)
  user_doc = {
    "discord_id" => discord_id,
    "user_type" => "student",
    "created_at" => Time.utc,
    "updated_at" => Time.utc,
    "is_active" => true,
    "student_data" => {
      "progress_level" => 1,
      "total_exp" => 0,
      "current_exp" => 0,
      "scores" => [] of Hash(String, JSON::Any),
      "quests" => [] of Hash(String, JSON::Any),
      "assessments_required" => [] of Hash(String, JSON::Any),
      "badges" => [] of Hash(String, JSON::Any)
    }
  }
  DatabaseService.insert_one("users", user_doc)
end
```

### Quest Management

```crystal
# Add quest to student
def assign_quest(discord_id : String, quest_id : String)
  quest_data = {
    "quest_id" => quest_id,
    "status" => "not_started",
    "exp_gained" => 0,
    "started_at" => Time.utc,
    "completed_at" => nil,
    "progress_data" => {
      "steps_completed" => [] of String,
      "current_step" => nil,
      "notes" => ""
    }
  }
  
  DatabaseService.update_one("users", 
    {"discord_id" => discord_id}, 
    {"$push" => {"student_data.quests" => quest_data}}
  )
end

# Update quest progress
def update_quest_progress(discord_id : String, quest_id : String, status : String)
  DatabaseService.update_one("users",
    {"discord_id" => discord_id, "student_data.quests.quest_id" => quest_id},
    {"$set" => {
      "student_data.quests.$.status" => status,
      "student_data.quests.$.completed_at" => (status == "completed" ? Time.utc : nil)
    }}
  )
end
```

### Assessment Operations

```crystal
# Add assessment score
def record_assessment_score(discord_id : String, assessment_id : String, score : Int32, max_score : Int32)
  score_data = {
    "assessment_id" => assessment_id,
    "score" => score,
    "max_score" => max_score,
    "percentage" => (score.to_f / max_score.to_f * 100).round(2),
    "completed_at" => Time.utc,
    "attempts" => 1,
    "metadata" => {} of String => JSON::Any
  }
  
  DatabaseService.update_one("users",
    {"discord_id" => discord_id},
    {"$push" => {"student_data.scores" => score_data}}
  )
end

# Check if user has required level for assessment
def can_access_assessment?(discord_id : String, assessment_id : String) : Bool
  user = get_user(discord_id)
  return false unless user
  
  assessment = DatabaseService.find_one("assessments", {"assessment_id" => assessment_id})
  return false unless assessment
  
  user_level = user["student_data"]["progress_level"].as_i
  required_level = assessment["assessment_level"].as_i
  
  user_level >= required_level
end
```

---

## 🏆 Schema Benefits

### Document Database Advantages

- **Single Query Access**: Most user operations require only one database hit
- **Atomic Updates**: Array operations within documents are atomic
- **Flexible Schema**: Easy to add new fields without migrations
- **Rich Data Types**: Native support for arrays, nested objects, dates
- **No Joins**: Embedded data eliminates complex join operations

### Performance Features

- **Optimized Indexing**: Strategic indexes for common query patterns  
- **Efficient Aggregations**: Easy progress calculations and statistics
- **Scalable Design**: Handles growth in users, quests, and assessments
- **Fast Lookups**: Discord ID-based primary access pattern

### Crystal Integration Benefits

- **Type Safety**: Crystal's type system works well with structured documents
- **JSON Mapping**: Natural fit for document database operations
- **Performance**: Direct database driver access without ORM overhead
- **Flexibility**: Easy to adapt queries for different use cases

---

## 📊 Common Query Patterns

### Student Progress Tracking

```crystal
# Get student's current progress overview
def get_student_progress(discord_id : String)
  user = get_user(discord_id)
  return nil unless user && user["user_type"] == "student"
  
  {
    "level" => user["student_data"]["progress_level"],
    "total_exp" => user["student_data"]["total_exp"],
    "quests_completed" => user["student_data"]["quests"].as_a.count { |q| q["status"] == "completed" },
    "assessments_passed" => user["student_data"]["scores"].as_a.count { |s| s["percentage"].as_f >= 70 },
    "badges_earned" => user["student_data"]["badges"].as_a.size
  }
end
```

### Assessment Eligibility Check

```crystal
# Check what assessments a student can take
def get_available_assessments(discord_id : String)
  user = get_user(discord_id)
  return [] of Hash unless user
  
  user_level = user["student_data"]["progress_level"].as_i
  
  DatabaseService.find_many("assessments", {
    "assessment_level" => {"$lte" => user_level},
    "metadata.is_active" => true
  })
end
```

This schema provides a robust foundation for your Discord bot while maintaining the flexibility and performance benefits of document databases.