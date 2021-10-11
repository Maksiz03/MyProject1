namespace Mazes
{
	public static class PyramidMazeTask
	{
		public static void MoveOut(Robot robot, int width, int height)
		{
			int step = width - 3;
			for (int i = 0; i < height/4; i++)
			{
				Move(robot, Direction.Right, step);
				step -=2;
				Move(robot, Direction.Up, 2);
				Move(robot, Direction.Left, step);
				step -=2;
				if (!robot.Finished)
				    Move(robot, Direction.Up, 2);
			}	
		}
		private static void Move(Robot robot, Direction direction, int stepsCount)
        {
			for (var i = 0; i < stepsCount; i++)
				robot.MoveTo(direction);
        }
	}
}
