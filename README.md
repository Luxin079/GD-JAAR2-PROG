# GD-JAAR2-PROG


# M5

Functions, Methods, Parameters & return type.

PROG les 1: Herhaling Functions, Classes en Arrays.

![GD M5 PROG](https://github.com/user-attachments/assets/7a3049bb-6e66-4c9e-835d-6ebe34d694fe)

SCRIPT: https://github.com/Luxin079/kevin-en-mads-avontuurtje/blob/main/Assets/PROG%20SCRIPTS/balletje.cs 

PROG les 2: Action Events

![GD PROG OP 2](https://github.com/user-attachments/assets/0675e3ff-27c6-4faa-9572-780e73917f7c)

SCRIPT: https://github.com/Luxin079/kevin-en-mads-avontuurtje/blob/main/Assets/PROG%20SCRIPTS/cylinder.cs

PROG Les 3:

![GD PROG OP  3](https://github.com/user-attachments/assets/c846966d-09db-4657-aac8-4b5e1049881e)

SCRIPT: https://github.com/Luxin079/kevin-en-mads-avontuurtje/blob/main/Assets/PROG%20SCRIPTS/EnemySpawner.cs



# M6

Opdracht 1

Code Conventies in Unity

![M6 Prog op1](https://github.com/user-attachments/assets/023e9edb-6e44-45c4-82c7-37fef0afbac5)


![M6 Prog op1](https://github.com/user-attachments/assets/47480a1d-b1d4-4315-8de1-02064ba519ba)


Opdracht 2

Opdaracht Class Diagrams


```mermaid

classDiagram
    class BuildManager {
        -GameObject selectedTowerPrefab
        -GameObject previewTower
        -Renderer[] previewRenderers
        -MonoBehaviour[] previewBehaviours
        -Camera cam
        +float towerHeightOffset
        +string allowedTag
        +void SetSelectedTower(GameObject)
    }
    
    class GameManager {
        +int startingMoney
        +int money
        +TextMeshProUGUI moneyText
        +bool SpendMoney(int)
        +void AddMoney(int)
    }
    
    class MoneyManager {
        -TextMeshProUGUI moneyTxt
        -int startingMoney
        -int money
        +bool CanSpend(int)
        +void SpendMoney(int)
        +void AddMoney(int)
    }
    
    class GameHealthManager {
        -int maxLives
        -int currentLives
        -bool isGameOver
        -TextMeshProUGUI livesText
        -GameObject gameOverPanel
        +void LoseLife()
        +bool IsGameOver
        +int GetLives()
    }
    
    class WaveSpawner {
        -Wave[] waves
        -int currentWaveIndex
        -Transform spawnPoint
        -float timeBetweenWaves
        -float waveCountdown
        -bool isSpawning
        -TextMeshProUGUI waveText
        -int totalWaveCount
        -IEnumerator SpawnWave(Wave)
        -void SpawnEnemy(GameObject)
    }
    
    class WaypointHolder {
        +List~Transform~ wayPoints
        +List~Transform~ GetWayPoints()
    }
    
    class BombarioTower {
        +float range
        +float fireRate
        -float fireCountdown
        +string enemyTag
        +Transform firePoint
        +GameObject bulletPrefab
        -Transform target
        +Transform CurrentTarget
        +void UpdateTarget()
        +void Shoot()
    }
    
    class SniperinoTower {
        +float range
        +float fireRate
        -float fireCountdown
        +string enemyTag
        +Transform firePoint
        +GameObject bulletPrefab
        -Transform target
        +Transform CurrentTarget
        +void UpdateTarget()
        +void Shoot()
    }
    
    class ZaperinoTower {
        +float range
        +float fireRate
        -float fireCountdown
        +string enemyTag
        +Transform firePoint
        +GameObject bulletPrefab
        -Transform target
        +Transform CurrentTarget
        +void UpdateTarget()
        +void Shoot()
    }
    
    class TowerStatus {
        +int towerCost
    }
    
    class TowerButton {
        +GameObject towerPrefab
        -Button button
        -void OnButtonClick()
    }
    
    class FirePointAim {
        +BombarioTower tower
    }
    
    class BombarioBullet {
        +float speed
        +int damage
        -Transform target
        +void SetTarget(Transform)
    }
    
    class SniperinoBullet {
        +float speed
        +int damage
        +float lifeTime
        -Rigidbody2D rb
        +void Fire(Vector2)
    }
    
    class ZaperinoBullet {
        +float speed
        +float slowAmount
        +float slowDuration
        +int damage
        -Transform target
        +void SetTarget(Transform)
    }
    
    class EnemyMover {
        +float moveSpeed
        +int maxHealth
        -int currentHealth
        -List~Transform~ waypoints
        -int currentIndex
        -float currentSpeed
        -Coroutine slowRoutine
        +bool TakeDamage(int)
        +void ApplySlow(float, float)
        -IEnumerator SlowEffect(float, float)
    }
    
    class Wave {
        +string waveName
        +EnemyGroup[] enemyGroups
    }
    
    class EnemyGroup {
        +GameObject enemyPrefab
        +int count
        +float spawnRate
    }
    
    BuildManager --> TowerStatus
    BuildManager --> MoneyManager
    TowerButton --> BuildManager
    BombarioTower --> BombarioBullet
    SniperinoTower --> SniperinoBullet
    ZaperinoTower --> ZaperinoBullet
    BombarioBullet --> EnemyMover
    SniperinoBullet --> EnemyMover
    ZaperinoBullet --> EnemyMover
    EnemyMover --> WaypointHolder
    EnemyMover --> GameHealthManager
    WaveSpawner --> EnemyMover
    WaveSpawner --> MoneyManager
    WaveSpawner --> GameHealthManager
    FirePointAim --> BombarioTower

```
