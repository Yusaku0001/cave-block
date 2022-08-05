<?php

namespace vulcania\task;

    use pocketmine\player\GameMode;
    use pocketmine\scheduler\Task;
    use pocketmine\player\Player;
    use pocketmine\math\Vector3;

    class Main extends PluginBase iimplements Listener{

        public function onEnable(): void
        {
            $this->getlogger()-<notice("le plugin  à bien été ajouté");
    }

        class CaveTask extends Task {

            private $player;
            private $state;

            public function __construct(Player $player){
                $this->player = $player;
                $this->state = "NotInCave";
            }

            public function onRun() : void{
                if($this->state != "None"){
                    if($this->state == "NotInCave")
                    {
                        $this->player->setGamemode(GameMode::SPECTATOR());
                        $this->player->teleport(new Vector3($this->player->getPosition()->getX(), $this->player->getPosition()->getY()-4, $this->player->getPosition()->getZ()));
                        $this->player->setImmobile(true);
                        $this->state = "InCave";
                    }
                    else{
                        $this->player->teleport(new Vector3($this->player->getPosition()->getX(), $this->player->getPosition()->getY()+4, $this->player->getPosition()->getZ()));
                        $this->player->setGamemode(GameMode::SURVIVAL());
                        $this->player->setImmobile(false);
                        $this->state = "None";
                    }
                }
            }

        }
